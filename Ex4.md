## Ex.No:4
## Ex.Name: Queue using Linked List – Insert and Delete Operations
## Date:
## Aim:
To write a C++ program to implement a Queue using Linked List, insert integer elements into the queue, and delete two items from the queue.

## Algorithm:
Start the program.

Create a queue using Linked List (STL or manual implementation).

Insert n integer elements into the queue.

Display the queue contents.

Perform two DeQueue operations (delete two items).

Display the updated queue.

Show the front and rear elements of the queue.

Stop the program.

## Program:
```
#include<bits/stdc++.h>
using namespace std;
struct QNode
{
    int data;
    QNode* next;
    QNode(int d)
    {
        data=d;
        next=NULL;
    }
};
struct Queue
{
    QNode *front,*rear;
    Queue()
    {
        front=rear=NULL;
    }
    void enQueue(int x)
    {
        QNode* temp = new QNode(x);
        if(rear == NULL)
        {
            front=rear=temp;
            return;
        }
        rear->next=temp;
        rear=temp;
    }
    void deQueue()
    {
        if(front == NULL)
            return;
        QNode* temp=front;
        front=front->next;
        
        if(front == NULL)
            rear=NULL;
        delete(temp);
    }
    void display()
    {
        if(front==NULL)
        {
            cout<<"Underflow."<<endl;
            return;
        }
        QNode* temp=front;
        while(temp)
        {
            cout<<temp->data<<" ";
            temp=temp->next;
        }
        cout<<endl;
    }
};
int main()
{
    Queue q;
    int n;
    int x;
    q.display();
    cin>>n;
    for(int i=0;i<n;i++)
    {
        cin>>x;
        q.enQueue(x);
    }
    cout<<"Queue :";
    q.display();
    cout<<"After DeQueue :";
    q.deQueue();
    q.deQueue();
    q.display();
    cout<<"Queue Front : "<<(q.front)->data<<endl;
    cout<<"Queue Rear : "<<(q.rear)->data;
    return 0;
}
```
## Output:
<img width="872" height="535" alt="image" src="https://github.com/user-attachments/assets/ec7364e1-d037-4407-8c3a-49553d71d9ad" />



## Result:
The Program Executed Successfully.
