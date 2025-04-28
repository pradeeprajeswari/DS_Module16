# Ex18 B-Tree
## DATE:27/03/2025
## AIM:
To write a C function to delete an element in a B Tree.
## Algorithm
1. Start 
2. Try to delete the item from the node using delValFromNode. If not found, print "Not present" and return. 
3. If the node's count is 0 after deletion, set tmp to the current node and update myNode to its first linker child. 
4. Free the tmp node. 
5. Update the global root to the new myNode. 
6. Return after deletion. 
7. End  

## Program:
```
/*
Program to write a C function to delete an element in a B Tree
Developed by: PRADEEP E
RegisterNumber:  212223230149
*/
```
```
int delValFromNode(int item, struct BTreeNode *myNode) {
  int pos, flag = 0;
  if (myNode) {
    if (item < myNode->item[1]) {
      pos = 0;
      flag = 0;
    } else {
      for (pos = myNode->count; (item < myNode->item[pos] && pos > 1); pos--)
        ;
      if (item == myNode->item[pos]) {
        flag = 1;
      } else {
        flag = 0;
      }
    }
    if (flag) {
      if (myNode->linker[pos - 1]) {
        copySuccessor(myNode, pos);
        flag = delValFromNode(myNode->item[pos], myNode->linker[pos]);
        if (flag == 0) {
          printf("Given data is not present in B-Tree\n");
        }
      } else {
        removeVal(myNode, pos);
      }
    } else {
      flag = delValFromNode(item, myNode->linker[pos]);
    }
    if (myNode->linker[pos]) {
      if (myNode->linker[pos]->count < MIN)
        adjustNode(myNode, pos);
    }
  }
  return flag;
}

void delete (int item, struct BTreeNode *myNode) {
    
  struct BTreeNode *tmp;
if(!delValFromNode(item,myNode))
{
    printf("Not present\n");
}
else
{
    if(myNode->count==0)
    {
        tmp=myNode;
        myNode=myNode->linker[0];
        free(tmp);
    }
}
root=myNode;
}

```

## Output:

![image](https://github.com/user-attachments/assets/b31147ff-ce46-4393-9d13-1a92ca489251)


## Result:
Thus, the C function to delete an element in a B Tree is implemented successfully.
