## 1. Using vector:
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
    ListNode* reverseList(ListNode* head) {
        ListNode* prev = NULL;
        ListNode* curr = head;

        while(curr != NULL)
        {
           ListNode* nextNode = curr->next; 
           curr->next = prev;
           prev = curr;
           curr = nextNode;

        }
        return prev;
        
    }
};
```
### 2. using prev
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
    ListNode* reverseList(ListNode* head) {  // assume that the node is [1,2,3,4,5]
        ListNode* prev = NULL; // END of the node is NULL
        ListNode* curr = head;

        while(curr != NULL){
           ListNode* nextNode = curr->next; // record the next node first.
           curr->next = prev; // link backward [loop 1: link to NULL],[loop 2: 1],[loop 3: 2]
           prev = curr; // update the prev(changing the starting point of prev). [loop 1: prev update from NULL to 1 (NULL > 1)], [loop 2: 1 update to 2], [loop 3: 2 update to 3]
           curr = nextNode; // move to the next node.
        }
        return prev;
    }
};
```
