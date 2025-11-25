## Ex.No:2
## Ex.Name: Insert five double elements into Stack using Linked List (STL)
## Date:
## Aim:
To write a C++ program to insert five double elements into a stack using the STL stack container (linked list based), and demonstrate stack operations (push, pop, top, and size).

## Algorithm:
Start the program.

Create an STL stack<double>.

Read n (number of elements).

Push n double values onto the stack.

Display the current size of the stack.

Display the top element of the stack.

Perform 1 pop operation and display the new top.

Perform another pop operation and display the new top.

Display the final size of the stack after two pops.

Stop the program.

## Program:
```
#include <bits/stdc++.h>
using namespace std;
template <typename T>


class Stack {
public:
	list<T> l;
	double cs = 0;
	void push(T d)
	{
		cs++;
		l.push_front(d);
	}
	
	void pop()
	{
		if (cs <= 0) {
			cout << "Stack empty" << endl;
		}
		else {
			cs--;
			l.pop_front();
		}
	}
	bool empty() 
	{ 
	    return cs == 0; 
	    
	}
	
	T top() { return l.front(); }
	double size()
	{
		return cs;
	}
	
	void print()
	{
		for (auto x: l) 
		{
			cout << x << endl;
		}
	}
};
int main()
{
    int n;
    float num;
    cin>>n;
	Stack<double> s;
	for(int i=0;i<n;i++)
	{


	    cin>>num;
	    s.push(num);
	}
	cout << "Current size of the stack is " << s.size() << endl;
	cout << "The top element of the stack is " << s.top() << endl;
	s.pop(); 
	cout << "The top element after 1 pop operation is " << s.top() << endl;
	s.pop();
	cout << "The top element after 2 pop operations is " << s.top() << endl;
	cout << "Size of the stack after 2 pop operations is " << s.size() << endl;
	return 0;
}
```
## Output:

<img width="862" height="545" alt="image" src="https://github.com/user-attachments/assets/a5f1215a-91f4-4966-b27f-62dd0be36078" />





## Result:
The Program Executed Successfully.
