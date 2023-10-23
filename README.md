#include<iostream>
using namespace std;

class Node{
    public:
    int data;
    Node* prev;
    Node* next;

    //constructor
    Node(int d){
        this -> data = d;
        this -> prev = NULL;
        this -> next = NULL;
    }
};

void insertatHead(Node* &head , int d){
    Node* temp = new Node(d);
    temp -> next = head;
    head -> prev = temp;
    head = temp;
}

void insertatTail(Node* &tail , int d){
    Node* temp = new Node(d);
    tail -> next = temp;
    temp -> prev = tail;
    tail = temp;
}

void print(Node* &head){
    Node* temp = head;

    while(temp != NULL){
        cout << temp -> data << " ";
        temp = temp -> next;
    }
    cout << endl;
}

int main(){
    Node* Node1 = new Node(10);
    
    Node* head = Node1;
    print(head);

    insertatHead(head , 20);
    print(head);

    insertatHead(head , 30);
    print(head);

    insertatHead(head , 40);
    print(head);

    insertatHead(head , 50);
    print(head);

    Node* tail = Node1;

    insertatTail(tail, 0);
    print(head);

    insertatTail(tail , 25);
    print(head);

    insertatTail(tail , 32);
    print(head);

    insertaTail(tail, 100);
    print(head);


    return 0;
}
