## Ex.No:3
## Ex.Name: Insert five special character elements in to stack
## Date:
## Aim:
To Write a CPP Program to insert five special character elements in to stack using linked list (use STL for Stack)

## Algorithm:
Start the program.

Create a base class Base with a virtual function print().

Create a derived class Derived that overrides the print() function.

Use a base class pointer to point to the derived class object.

Call the print() function to demonstrate runtime polymorphism (base pointer calls derived function).

Stop the program.

## Program:
```
#include <bits/stdc++.h>
using namespace std;
template <typename T>
// templating it so that any data type can be used

class Stack {
public:
	list<T> l;
	float cs = 0;
	// current size of the stack

	// pushing an element into the stack
	void push(T d)
	{
		cs++;
		// increasing the current size of the stack
		l.push_front(d);
	}
	// popping an element from the stack
	void pop()
	{
		if (cs <= 0) {
			// cannot pop us stack does not contain an
			// elements
			cout << "Stack empty" << endl;
		}
		else {
			// decreasing the current size of the stack
			cs--;
			l.pop_front();
		}
	}
	// if current size is 0 then stack is empty
	bool empty() 
	{ 
	    return cs == 0; 
	    
	}
	// getting the element present at the top of the stack
	T top() { return l.front(); }
	float size()
	{
		// getting the size of the stack
		return cs;
	}
	// printing the elements of the stack
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
    float n;
    char num;
    cin>>n;
	Stack<char> s;
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
<img width="1203" height="525" alt="image" src="https://github.com/user-attachments/assets/7dafd7bb-c8ba-4c78-b88f-3e5e03121121" />


## Result:
The Program Executed Successfully.
