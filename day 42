/*Problem Statement:
Given a queue of integers, reverse the queue using a stack.

Input Format:
- First line contains integer N
- Second line contains N space-separated integers

Output Format:
- Print the reversed queue

Example:
Input:
5
10 20 30 40 50

Output:
50 40 30 20 10*/
#include <stdio.h>

int main()
{
    int n, i;
    int queue[100];
    int stack[100];
    int top = -1;

    scanf("%d", &n);

    for(i = 0; i < n; i++)
    {
        scanf("%d", &queue[i]);
    }
    for(i = 0; i < n; i++)
    {
        stack[++top] = queue[i];
    }
    for(i = 0; i < n; i++)
    {
        queue[i] = stack[top--];
    }
    for(i = 0; i < n; i++)
    {
        printf("%d ", queue[i]);
    }

    return 0;
}
