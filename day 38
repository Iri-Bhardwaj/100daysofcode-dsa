/*Problem: Deque (Double-Ended Queue)

A Deque is a linear data structure that allows insertion and deletion of elements from both the front and the rear. It provides more flexibility than a standard queue or stack.

Common Operations:
1. push_front(value): Insert an element at the front of the deque.
2. push_back(value): Insert an element at the rear of the deque.
3. pop_front(): Remove an element from the front of the deque.
4. pop_back(): Remove an element from the rear of the deque.
5. front(): Return the front element of the deque.
6. back(): Return the rear element of the deque.
7. empty(): Check whether the deque is empty.
8. size(): Return the number of elements in the deque.

Additional Operations:
- clear(): Remove all elements from the deque.
- erase(): Remove one or more elements from the deque.
- swap(): Swap contents of two deques.
- emplace_front(): Insert an element at the front without copying.
- emplace_back(): Insert an element at the rear without copying.
- resize(): Change the size of the deque.
- assign(): Replace elements with new values.
- reverse(): Reverse the order of elements.
- sort(): Sort the elements in ascending order.

Time Complexity:
- push_front, push_back, pop_front, pop_back, front, back, empty, size: O(1)
- clear, erase, resize, assign, reverse: O(n)
- sort: O(n log n)

Input:
- Sequence of deque operations with values (if applicable)

Output:
- Results of operations such as front, back, size, or the final state of the deque after all operations*/
#include <stdio.h>

#define MAX 100

int deque[MAX];
int front = -1;
int rear = -1;

void push_front(int x)
{
    if(front == 0)
        printf("Deque Overflow\n");
    else
    {
        if(front == -1)
        {
            front = rear = 0;
        }
        else
        {
            front--;
        }
        deque[front] = x;
    }
}

void push_back(int x)
{
    if(rear == MAX-1)
        printf("Deque Overflow\n");
    else
    {
        if(front == -1)
        {
            front = rear = 0;
        }
        else
        {
            rear++;
        }
        deque[rear] = x;
    }
}

void pop_front()
{
    if(front == -1)
        printf("Deque Underflow\n");
    else
    {
        printf("Deleted: %d\n", deque[front]);

        if(front == rear)
            front = rear = -1;
        else
            front++;
    }
}

void pop_back()
{
    if(rear == -1)
        printf("Deque Underflow\n");
    else
    {
        printf("Deleted: %d\n", deque[rear]);

        if(front == rear)
            front = rear = -1;
        else
            rear--;
    }
}

void show_front()
{
    if(front == -1)
        printf("Deque Empty\n");
    else
        printf("Front element: %d\n", deque[front]);
}

void show_back()
{
    if(rear == -1)
        printf("Deque Empty\n");
    else
        printf("Rear element: %d\n", deque[rear]);
}

void size()
{
    if(front == -1)
        printf("Size: 0\n");
    else
        printf("Size: %d\n", rear-front+1);
}

void display()
{
    if(front == -1)
        printf("Deque Empty\n");
    else
    {
        for(int i=front;i<=rear;i++)
            printf("%d ",deque[i]);
        printf("\n");
    }
}

int main()
{
    int choice, value;

    while(1)
    {
        printf("\n1.Push Front\n2.Push Back\n3.Pop Front\n4.Pop Back\n5.Front\n6.Back\n7.Size\n8.Display\n9.Exit\n");
        scanf("%d",&choice);

        switch(choice)
        {
            case 1:
                printf("Enter value: ");
                scanf("%d",&value);
                push_front(value);
                break;

            case 2:
                printf("Enter value: ");
                scanf("%d",&value);
                push_back(value);
                break;

            case 3:
                pop_front();
                break;

            case 4:
                pop_back();
                break;

            case 5:
                show_front();
                break;

            case 6:
                show_back();
                break;

            case 7:
                size();
                break;

            case 8:
                display();
                break;

            case 9:
                return 0;
        }
    }
}
