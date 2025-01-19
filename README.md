# Final-assignment-
#include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;

    Node(int data) {
        this->data = data;
        this->next = nullptr;
    }
};
class Stack {
private:
    Node* top;

public:
    Stack() {
        top = nullptr;
    }

    void push(int data) {
        Node* newNode = new Node(data);
        newNode->next = top;
        top = newNode;
    }

    int pop() {
        if (top == nullptr) {
            cout << "Stack is empty" << endl;
            return -1;
        }
        int poppedData = top->data;
        Node* temp = top;
        top = top->next;
        delete temp;
        return poppedData;
    }

    bool isEmpty() {
        return top == nullptr;
    }

    int peek() {
        if (top == nullptr) {
            cout << "Stack is empty" << endl;
            return -1;
        }
        return top->data;
    }
};
class Queue {
private:
    Node* front;
    Node* rear;

public:
    Queue() {
        front = rear = nullptr;
    }

    void enqueue(int data) {
        Node* newNode = new Node(data);
        if (rear == nullptr) {
            front = rear = newNode;
            return;
        }
        rear->next = newNode;
        rear = newNode;
    }

    int dequeue() {
        if (front == nullptr) {
            cout << "Queue is empty" << endl;
            return -1;
        }
        int dequeuedData = front->data;
        Node* temp = front;
        front = front->next;

        if (front == nullptr) {
            rear = nullptr;
        }
        delete temp;
        return dequeuedData;
    }

    bool isEmpty() {
        return front == nullptr;
    }

    int peek() {
        if (front == nullptr) {
            cout << "Queue is empty" << endl;
            return -1;
        }
        return front->data;
    }
};
int main() {
    Stack stack;
    stack.push(86);
    stack.push(45);
    stack.push(28);
    cout << "Stack Peek: " << stack.peek() << endl;
    cout << "Stack Pop: " << stack.pop() << endl;
    cout << "Stack Pop: " << stack.pop() << endl;
    cout << "Stack IsEmpty: " << (stack.isEmpty() ? "true" : "false") << endl;
    Queue queue;
    queue.enqueue(47);
    queue.enqueue(78);
    queue.enqueue(50);
    cout << "Queue Peek: " << queue.peek() << endl;
    cout << "Queue Dequeue: " << queue.dequeue() << endl;
    cout << "Queue Dequeue: " << queue.dequeue() << endl;
    cout << "Queue IsEmpty: " << (queue.isEmpty() ? "true" : "false") << endl;

    return 0;
}
