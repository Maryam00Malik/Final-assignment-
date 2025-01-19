# Final-assignment-
#include <iostream>

// Node class
class Node {
public:
    int data;
    Node* next;

    Node(int value) {
        data = value;
        next = nullptr;
    }
};

// Stack class
class Stack {
private:
    Node* top;

public:
    Stack() {
        top = nullptr;
    }

    // Push element onto the stack
    void push(int value) {
        Node* newNode = new Node(value);
        newNode->next = top;
        top = newNode;
    }

    // Pop element from the stack
    int pop() {
        if (top == nullptr) {
            std::cout << "Stack is empty!" << std::endl;
            return -1;
        }
        int value = top->data;
        Node* temp = top;
        top = top->next;
        delete temp;
        return value;
    }

    // Peek at the top element of the stack
    int peek() {
        if (top == nullptr) {
            std::cout << "Stack is empty!" << std::endl;
            return -1;
        }
        return top->data;
    }

    // Check if the stack is empty
    bool isEmpty() {
        return top == nullptr;
    }
};

// Queue class
class Queue {
private:
    Node* front;
    Node* rear;

public:
    Queue() {
        front = nullptr;
        rear = nullptr;
    }

    // Enqueue element into the queue
    void enqueue(int value) {
        Node* newNode = new Node(value);
        if (rear == nullptr) {
            front = rear = newNode;
        } else {
            rear->next = newNode;
            rear = newNode;
        }
    }

    // Dequeue element from the queue
    int dequeue() {
        if (front == nullptr) {
            std::cout << "Queue is empty!" << std::endl;
            return -1;
        }
        int value = front->data;
        Node* temp = front;
        front = front->next;
        if (front == nullptr) {
            rear = nullptr;
        }
        delete temp;
        return value;
    }

    // Peek at the front element of the queue
    int peek() {
        if (front == nullptr) {
            std::cout << "Queue is empty!" << std::endl;
            return -1;
        }
        return front->data;
    }

    // Check if the queue is empty
    bool isEmpty() {
        return front == nullptr;
    }
};

int main() {
    // Create a stack and queue
    Stack stack;
    Queue queue;

    // Push elements onto the stack
    stack.push(1);
    stack.push(2);
    stack.push(3);

    // Enqueue elements into the queue
    queue.enqueue(1);
    queue.enqueue(2);
    queue.enqueue(3);

    // Pop elements from the stack
    std::cout << "Popped from stack: " << stack.pop() << std::endl;
    std::cout << "Popped from stack: " << stack.pop() << std::endl;
    std::cout << "Popped from stack: " << stack.pop() << std::endl;

    // Dequeue elements from the queue
    std::cout << "Dequeued from queue: " << queue.dequeue() << std::endl;
    std::cout << "Dequeued from queue: " << queue.dequeue() << std::endl;
    std::cout << "Dequeued from queue: " << queue.dequeue() << std::endl;

    return 0;
}
Time Complexity The time complexity of the Stack and Queue operations is as follows:

Stack:
Push: O(1)
Pop: O(1)
Peek: O(1)
Is Empty: O(1)
Queue:
Enqueue: O(1)
Dequeue: O(1)
Peek: O(1)
Is Empty: O(1)
LinkedIn Post

I'm excited to share my recent assignment on implementing a Stack and Queue data structure using a Linked List in C++!

This project helped me develop my problem-solving skills and understand the importance of data structures in software development. I implemented the Stack and Queue operations from scratch, ensuring that the code is efficient, well-documented, and easy to understand.

The time complexity of the Stack and Queue operations is O(1), making them efficient for large-scale applications.

I'm proud of what I've accomplished, and I'm looking forward to applying
