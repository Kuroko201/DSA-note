## Usage：
Find whether a loop exist in a linked list

## Method:
  1.We will first creat two pointer: Node* slow = head,  Node* fast = head.
  
  2.Then, we move these pointer at different speed: slow = slow->next; fast = fast->next->next;
  
  3.If there is loop existed, the fast pointer will be the same position as the slow pointer eventually.

## Linked_List with cycle existed:
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
