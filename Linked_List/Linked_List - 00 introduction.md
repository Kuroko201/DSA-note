## Why we use linked list?
  1. When we don't know how many element will be in the list
  2. Constant-time insertions/deletions from the list O(1), while array takes O(N)
     
## When we use array?
  1. Array will be used when need random access to elements
  2. Array will be used when you know how many element you need.  array[100] > you know there will be 100 elements.
  3. Array can apply arithmetic operations. > Sorting alogrithm...

## Sample example of linked list (C++)
```
#include<iostream>

struct Node{ // linked list
    int age;
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
   curr = curr->next; // Move to the next position(node) of linked next
   
   curr -> age = 13; // assgin value the the current node.
   curr-> next = new Node(); // create more node.
   curr = curr->next; // Move to the next position(node) of linked next
   
   curr -> age = 18; // assgin value the the current node.
   curr -> next = NULL; // End of the linked list
   print(head); // print the linked list.
   
   delete head; // use delete to release the memory.

   return 0;
}
```
![image](https://github.com/Kuroko201/DSA-note/blob/8dc38b3450fd9e970f9fa9116e781a4081f171a2/Linked_List/pic/IMG_4695.jpg =250x250)
