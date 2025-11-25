## Ex.No:1
## Ex.Name: Infix to Prefix Conversion using Linked List Stack STL
## Date:
## Aim:
To write a C++ program to convert an infix expression into a prefix expression using a stack implemented with STL (Linked List based).

## Algorithm:
Start the program.

Define precedence rules for operators (+, -, *, /, ^).

Reverse the given infix expression and swap parentheses.

Use a stack (STL stack<char>) to convert the modified expression into postfix:

Push operators into stack based on precedence.

Append operands directly to the result string.

Pop stack contents when higher or equal precedence operators are found.

Handle parentheses properly.

Reverse the postfix expression to obtain prefix form.

Display the prefix expression.

Stop the program.

## Program:
```
#include<bits/stdc++.h>
using namespace std;
int precedence(char ch){  
    if(ch=='+' || ch=='-')    {     
        return 1;   
    }    
    else if(ch=='*' || ch=='/')    {       
        return 2;   
    }    
    else    {        
        return 3;   
    }
    
}
int main(){    
    stack<char> s;    
    int length=0,t;    
    string infix,prefix="";    
    cin>>infix;    
    length=infix.length();   
    reverse(infix.begin(),infix.end());    
    for(int i=0;i<length;i++)    {        
        t=precedence(infix[i]);        
        if(t==3)        {            
            prefix=prefix+infix[i];            
            continue;        
            
        }       
        else        {            
            if(s.empty() || t>=precedence(s.top()))            {              
                s.push(infix[i]);                
                continue;           
            }           
            else            {             
                while(!s.empty() && t<precedence(s.top()))                {                   
                    prefix= prefix + s.top();                    
                    s.pop();                
                    
                }                
                s.push(infix[i]);                
                continue;            
                
            }        
            
        }    
        
    }    
    while(!s.empty())    {       
        prefix = prefix + s.top();        
        s.pop();    
        
    }    
    reverse(prefix.begin(),prefix.end());    
    cout<<prefix;   
    return 0;
    
}
```
## Output:

<img width="862" height="384" alt="image" src="https://github.com/user-attachments/assets/5d838697-5130-4cba-a280-3ef2fb5b8f05" />


## Result:
The Program Executed Successfully.
