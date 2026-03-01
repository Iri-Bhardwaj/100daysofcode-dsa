/*Problem: Rotate Linked List Right by k Places - Implement using linked list with dynamic memory allocation.

Input:
- First line: integer n
- Second line: n space-separated integers
- Third line: integer k

Output:
- Print the linked list elements after rotation, space-separated

Example:
Input:
5
10 20 30 40 50
2

Output:
40 50 10 20 30

Explanation:
Connect last node to head forming circular list. Traverse to (n-k)th node, set next to NULL, update head to (n-k+1)th node.*/
#include <stdio.h>
#include <stdlib.h>

struct Node{
    int data;
    struct Node* next;
};

struct Node* rotate(struct Node* head, int k){
    if(!head || k==0) return head;

    struct Node *temp = head;
    int n = 1;

    while(temp->next){
        temp = temp->next;
        n++;
    }

    temp->next = head;
    k = k % n;
    int steps = n - k;

    temp = head;
    for(int i = 1; i < steps; i++)
        temp = temp->next;

    head = temp->next;
    temp->next = NULL;

    return head;
}

int main(){
    int n, k, x;
    scanf("%d",&n);

    struct Node *head=NULL,*tail=NULL,*newNode;

    for(int i=0;i<n;i++){
        scanf("%d",&x);
        newNode = malloc(sizeof(struct Node));
        newNode->data = x;
        newNode->next = NULL;

        if(!head) head = tail = newNode;
        else{
            tail->next = newNode;
            tail = newNode;
        }
    }

    scanf("%d",&k);
    head = rotate(head,k);

    while(head){
        printf("%d ",head->data);
        head = head->next;
    }
}
