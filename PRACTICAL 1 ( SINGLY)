#include <iostream>
using namespace std;

struct SNode {
    int data;
    SNode* next;
    SNode(int x) : data(x), next(nullptr) {}
};

class SinglyLinkedList {
    SNode* head;
public:
    SinglyLinkedList() : head(nullptr) {}

    void insertAtBeginning(int x) {
        SNode* n = new SNode(x);
        n->next = head;
        head = n;
    }

    void insertAtPosition(int x, int pos) {
        if (pos <= 1 || head == nullptr) {
            insertAtBeginning(x);
            return;
        }
        SNode* cur = head;
        for (int i = 1; i < pos - 1 && cur->next != nullptr; i++)
            cur = cur->next;
        SNode* n = new SNode(x);
        n->next = cur->next;
        cur->next = n;
    }

    void removeFromBeginning() {
        if (head == nullptr) return;
        SNode* temp = head;
        head = head->next;
        delete temp;
    }

    void removeFromPosition(int pos) {
        if (head == nullptr) return;
        if (pos <= 1) {
            removeFromBeginning();
            return;
        }
        SNode* cur = head;
        for (int i = 1; i < pos - 1 && cur->next != nullptr; i++)
            cur = cur->next;
        if (cur->next == nullptr) return;
        SNode* temp = cur->next;
        cur->next = temp->next;
        delete temp;
    }

    SNode* search(int x) {
        SNode* cur = head;
        while (cur != nullptr) {
            if (cur->data == x) return cur;
            cur = cur->next;
        }
        return nullptr;
    }

    void display() {
        SNode* cur = head;
        while (cur != nullptr) {
            cout << cur->data << " -> ";
            cur = cur->next;
        }
        cout << "NULL\n";
    }
};

int main() {
    SinglyLinkedList list;
    int choice, x, pos;
    while (true) {
        cout << "\n1.Insert at beginning\n2.Insert at position\n3.Remove from beginning\n4.Remove from position\n5.Search\n6.Display\n7.Exit\n";
        cin >> choice;
        if (choice == 1) {
            cin >> x; list.insertAtBeginning(x);
        } else if (choice == 2) {
            cin >> x >> pos; list.insertAtPosition(x, pos);
        } else if (choice == 3) list.removeFromBeginning();
        else if (choice == 4) {
            cin >> pos; list.removeFromPosition(pos);
        } else if (choice == 5) {
            cin >> x;
            if (list.search(x)) cout << "Found\n"; else cout << "Not found\n";
        } else if (choice == 6) list.display();
        else if (choice == 7) break;
    }
}
