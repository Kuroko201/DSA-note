## Usage：
Find whether a loop exist in a linked list
Find the middle of the linked list
## Method:
  1.We will first creat two pointer: Node* slow = head,  Node* fast = head.
  
  2.Then, we move these pointer at different speed: slow = slow->next; fast = fast->next->next;
  
  3.If there is loop existed, the fast pointer will be the same position as the slow pointer eventually.

## Linked list with cycle existed:
<img src="https://github.com/Kuroko201/DSA-note/blob/main/Linked_List/pic/linked_list_cycle.png?raw=true" width="600px">

## Sample Code (C++, LeetCode 141 Linked List Cycle)
```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    bool hasCycle(ListNode *head) {
        if(head == NULL)return false; 
        else if(head->next == NULL)return false;
        ListNode* slow = head;
        ListNode* fast = head;
        while(fast!= NULL && fast->next != NULL ){ 
            slow = slow->next;
            fast = fast->next->next;
            if(slow == fast)return true;
        }
        return false;
    }
};
```
## Sample Code (C++, LeetCode 876 Middle of the Linked List)
```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* middleNode(ListNode* head) {
        ListNode* slow = head;
        ListNode* fast = head;
        while(fast != NULL && fast->next != NULL){
            slow = slow->next;
            fast = fast->next->next;
        }
        return slow;
    }
};
```
