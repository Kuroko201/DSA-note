## Why we use linked list?
   Constant-time insertions/deletions O(1), while array takes O(N). In array, if you want to delete or change from the array (except you want to change the tails of the array),  you need to move or backward everything in the array
     
## When we use array?
  1. Array will be used when need random access to elements. You know you need to get somethings from array[i] (O(1)). In array, once you know the position, we can easy access that data. In linked list, we have to run the whole linked list (O(N))
  3. Array can apply arithmetic operations. > Sorting alogrithm...

## Linked list is not contiguous:
  for example: [10,20,30,40,50]
  
  In array, we can access the value by arr[0], arr[1], arr[3]...  We know exactly where is the first element, the second element.
  
  In linked list, we don't know where are the elements. We need pointers to store the memory location of each value. And link them.
  
  In linked list, <b> two things will be stored. One is the Value, one is a pointer that point to the next memory location. </b>


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
   //use  "new"  to allocate memory to a linked list with datatype Node
   Node* M5 = new Node(50,NULL); // END OF THE NODE
   Node* M4 = new Node(40,M5); // point to the next memory location M5
   Node* M3 = new Node(30,M4); // point to the next memory location M4
   Node* M2 = new Node(20,M3); // point to the next memory location M3
   Node* M1 = new Node(10,M2); // Start of the Node, point to the next memory location M2.
   print(M1); // print the linked list from the starting point
   // we need to remember the starting point to print the whole linked list

   delete M1; // release memory.
   return 0;
}
```
<img src="https://github.com/Kuroko201/DSA-note/blob/main/Linked_List/pic/linked_List%20-%2001.png?raw=true" width="600px">

## Simple example of linked list (C++) 2 - using struct
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
   // we need to remember the starting point to print the whole linked list

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
## Simple example of linked list (C++) 3 - using function
```
#include<iostream>

class Node{
    public:
        int age;
        Node* next;
        
        Node(int value, Node* next1){
            age = value;
            next = next1;
        }
        Node(int value){
            age = value;
            next = nullptr;
        }
};

Node* arr_to_Linked_List(int arr[], int arr_size){
            Node* head = new Node(arr[0]);
            Node* curr = head;
            for(int i = 1; i < arr_size; i++){
                Node* temp = new Node(arr[i]); // make new node with value arr[i]
                curr->next = temp; // store the pointer that point to the next memory location
                curr = temp; // move to the next new node.
            }
            return head;
        }
        
void print(Node* node){  // print the linked list
    while(node != NULL){ // when not reach the end of the linked list.
        std::cout << node->age << "\n";
        node = node->next;
    }
}

int main(){
   int arr[] = {1,3,5,7,9};
   int size = sizeof(arr) / sizeof(arr[0]);
   Node* head = arr_to_Linked_List(arr, size);
   print(head); // print the linked list from the starting point
   return 0;
}
```
