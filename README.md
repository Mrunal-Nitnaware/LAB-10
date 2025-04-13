# LAB-10
write a c program to find the middle element of singly linked list without using length of linked list
#include<stdio.h> 
#include<stdlib.h> 
 

struct Node 
{ 
    int data; 
    struct Node* next; 
}; 
 

void printMiddle(struct Node *head) 
{ 
    struct Node *slow_ptr = head; 
    struct Node *fast_ptr = head; 
 
    if (head!=NULL) 
    { 
        while (fast_ptr != NULL && 
               fast_ptr->next != NULL) 
        { 
            fast_ptr = fast_ptr->next->next; 
            slow_ptr = slow_ptr->next; 
        } 
        printf("The middle element is [%d]", 
                slow_ptr->data); 
    } 
} 
 
void push(struct Node** head_ref, 
          int new_data) 
{ 
   
    struct Node* new_node = 
           (struct Node*) malloc(sizeof(struct Node)); 
 

    new_node->data = new_data; 
 
 
    new_node->next = (*head_ref); 
 
    
    (*head_ref) = new_node; 
} 
 

void printList(struct Node *ptr) 
{ 
    while (ptr != NULL) 
    { 
        printf("%d->", ptr->data); 
        ptr = ptr->next; 
    } 
    printf("NULL"); 
} 
 

int main() 
{ 
    
    struct Node* head = NULL; 
    int i; 
 
    for (i = 5; i > 0; i--) 
    { 
        push(&head, i); 
        printList(head); 
        printMiddle(head); 
    } 
    return 0; 
} 

Delete A NODE FROM SINGLY LINKED LIST WHERE ONLY SINGLE POINTER OF THAT NODE IS GIVEN

#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};


void deleteNode(struct Node* delNode ) {
    
    
    if (delNode  == NULL || delNode ->next == NULL) {
        return;  
    }

    
    struct Node* temp = delNode ->next;
    delNode ->data = temp->data;


    delNode ->next = temp->next;

    
    free(temp);
}

void printList(struct Node* head) {
    struct Node* curr = head;
    while (curr != NULL) {
        printf("%d ", curr->data);
        curr = curr->next;
    }
    printf("\n");
}

struct Node* createNode(int x) {
    struct Node* new_node
        = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = x;
    new_node->next = NULL;
    return new_node;
}

int main() {
    
    
     struct Node* head = createNode(4);
    head->next = createNode(5);
    head->next->next = createNode(6);
    head->next->next->next = createNode(7);
    head->next->next->next->next = createNode(8);

    deleteNode(head);

    printList(head);

    return 0;
}

REVERSE CONTENT OF STACK USING RECURSSSION WITHOUT USING EXTRA ARRAY 
