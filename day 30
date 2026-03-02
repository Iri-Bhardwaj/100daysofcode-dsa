/*You are given two non-empty linked lists representing two non-negative integers. The most significant digit comes first and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

 

Example 1:


Input: l1 = [7,2,4,3], l2 = [5,6,4]
Output: [7,8,0,7]
Example 2:

Input: l1 = [2,4,3], l2 = [5,6,4]
Output: [8,0,7]
Example 3:

Input: l1 = [0], l2 = [0]
Output: [0]
 

Constraints:

The number of nodes in each linked list is in the range [1, 100].
0 <= Node.val <= 9
It is guaranteed that the list represents a number that does not have leading zeros.*/

#include <stdio.h>
#include <stdlib.h>

struct ListNode {
    int val;
    struct ListNode *next;
};

struct ListNode* createNode(int val) {
    struct ListNode* newNode = (struct ListNode*)malloc(sizeof(struct ListNode));
    newNode->val = val;
    newNode->next = NULL;
    return newNode;
}

struct ListNode* addTwoNumbers(struct ListNode* l1, struct ListNode* l2) {
    int s1[100], s2[100];
    int t1 = -1, t2 = -1;
    while (l1) { s1[++t1] = l1->val; l1 = l1->next; }
    while (l2) { s2[++t2] = l2->val; l2 = l2->next; }
    struct ListNode* head = NULL;
    int carry = 0;
    while (t1 >= 0 || t2 >= 0 || carry) {
        int sum = carry + (t1 >= 0 ? s1[t1--] : 0) + (t2 >= 0 ? s2[t2--] : 0);
        struct ListNode* node = (struct ListNode*)malloc(sizeof(struct ListNode));
        node->val = sum % 10;
        node->next = head;
        head = node;
        carry = sum / 10;
    }
    return head;
}

void printList(struct ListNode* head) {
    while (head) {
        printf("%d ", head->val);
        head = head->next;
    }
    printf("\n");
}

int main() {
    struct ListNode* l1 = createNode(7);
    l1->next = createNode(2);
    l1->next->next = createNode(4);
    l1->next->next->next = createNode(3);

    struct ListNode* l2 = createNode(5);
    l2->next = createNode(6);
    l2->next->next = createNode(4);

    struct ListNode* result = addTwoNumbers(l1, l2);
    printList(result);

    return 0;
}
