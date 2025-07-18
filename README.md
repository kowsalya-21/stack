#ifndef STACKS_CUSTOM_H
#define STACKS_CUSTOM_H
#include <iostream>
#include <cstdlib>
using namespace std; 
struct node {
    int data;
    node *next;
};
node *top = NULL;
void push(int val) {
    node* newnode = (node*)malloc(sizeof(node));
    if (newnode == NULL) {
        return;
    }
    newnode->data=val;
    newnode->next=top;
    top=newnode;
}

void pop() {
    node* temp;
    if (top == NULL) {
		return;
    } else {
        temp=top;
        cout<<"Popped element: "<<temp->data<<endl;
        top=top->next;
        free(temp);
    }
}

void display() {
    node* temp;
    if (top==NULL) {
    	return;
    } else {
        temp=top;
        cout<<"Stack elements ";
        while(temp != NULL) {
            cout<<temp->data<< " ";
            temp = temp->next;
        }
        cout<<endl;
    }
}


#endif
