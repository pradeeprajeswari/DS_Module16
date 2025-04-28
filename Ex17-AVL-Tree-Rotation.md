# Ex17 AVL Tree – Rotation
## DATE:24/03/2025
## AIM:
To write a C function to perform right rotation in an AVL Tree.

## Algorithm
1. Start 
2. Set y to the left child of x. 
3. Set the left child of x to be the right child of y. 
4. Set the right child of y to be x. 
5. Update the height of x and y. 
6. Return y as the new root after rotation. 
7. End  
## Program:
```
/*
Program to perform right rotation in AVL Tree
Developed by: PRADEEP E
RegisterNumber:  212223230149
*/
```
```
node * rotateright(node *x)
{
node *y;
y=x->left;
x->left=y->right;
y->right=x;
x->ht=height(x);
y->ht=height(y);
return(y);
}
 
```
## Output:

![image](https://github.com/user-attachments/assets/6d08a939-393a-4526-acab-6cbff4a67f77)


## Result:
Thus, the function to perform right rotation in an AVL Tree is implemented successfully.
