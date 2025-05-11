## Why we use linked list?
  1. When we don't know how many element will be in the list
  2. Constant-time insertions/deletions from the list O(1), while array takes O(N)
     
## When we use array?
  1. Array will be used when need random access to elements
  2. Array will be used when you know how many element you need.  array[100] > you know there will be 100 elements.
  3. Array can apply arithmetic operations. > Sorting alogrithm...

## Linked list is not contiguous:
  for example: [10,20,30,40,50]
  
  In array, we can access the value by arr[0], arr[1], arr[3]...  We know exactly where is the first element, the second element.
  
  In linked list, we don't know where are the elements. We need pointers to store the memory location of each value. And link them.
  
  In linked list, two things will be stored. One is the Value, one is a pointer that point to the next memory location.


## Simple example of linked list (C++) 1 - using class
```
#include<iostream>

class Node{ // linked list
    public:
        int age; // the data, we can later use "(ClassObject)->age" to get or assgin a value.
        Node* next; // link to the next node
        
        Node(int value, Node* next1){ // constructer
            age = value;
            next = next1;
        }
};


void print(Node* node){  // print the linked list
    while(node != NULL){ // when not reach the end of the linked list.
        std::cout << node->age << "\n";  // use "->age" to get the value
        node = node->next;
    }
}

int main(){
   //use  "new"  to allocate a memory to a linked list with datatype Node
   Node* M5 = new Node(50,NULL); // END OF THE NODE
   Node* M4 = new Node(40,M5); // point to the next memory location M5
   Node* M3 = new Node(30,M4); // point to the next memory location M4
   Node* M2 = new Node(20,M3); // point to the next memory location M3
   Node* M1 = new Node(10,M2); // Start of the Node, point to the next memory location M2.
   print(M1); // print the linked list
   delete M1; // release memory.
   return 0;
}
```
<img src="https://github.com/Kuroko201/DSA-note/blob/main/Linked_List/pic/linked_List%20-%2001.png?raw=true" width="600px">

## Simple example of linked list (C++) 2 - using class struct
```
#include<iostream>

struct Node{ // linked list
    int age; we can later use "(ClassObject)->age" to get or assgin a value.
    struct Node* next; // link to the next node
};

void print(Node* node){  // print the linked list
    while(node != NULL){ // when not reach the end of the linked list.
        std::cout << node->age << "\n";
        node = node->next;
    }
}

int main(){
   Node* head = new Node();//use new to allocate a memory to a linked list with datatype Node. Use a ptr(*) "head" to point at the start of the linked list
   Node* curr = head; // Create a new ptr curr to point at the current position. 
   //it's basically a two pointer. One pointer point at the head and remain still. One pointer will keep pointing diffrent position.
   
   curr -> age = 10; // assgin value the the current node.
   curr-> next = new Node(); // create more node.
   curr = curr->next; // Move to the next position(node) of linked next. This node will store the memory location to the next value
   
   curr -> age = 13; // assgin value the the current node.
   curr-> next = new Node(); // create more node.
   curr = curr->next; // Move to the next position(node) of linked next. This node will store the memory location to the next value
   
   curr -> age = 18; // assgin value the the current node.
   curr -> next = NULL; // End of the linked list
   print(head); // print the linked list.
   
   delete head; // use delete to release the memory.

   return 0;
}
```


