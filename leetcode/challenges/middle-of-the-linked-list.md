# Middle of the Linked List

## The Problem

Given the `head` of a singly linked list, return _the middle node of the linked list_.

If there are two middle nodes, return **the second middle** node.

## My Solution

```
class Solution {
public:
    ListNode* middleNode(ListNode* head) {
        double count=0;
        ListNode *traveller = head;
        while (traveller->next){
            count++;
            traveller= traveller->next;
        }

        count/=2.0;
        traveller = head;

        for (int i=0; i<count;i++){
            traveller = traveller->next;
        }

        return traveller;
        
    }
};
```

<figure><img src="../../.gitbook/assets/Screenshot 2023-07-01 171544.png" alt=""><figcaption></figcaption></figure>

## Rationale

Simply counting the elements in the list and dividing that by 2 worked to get the halfway point of the list. The only slight road bump was changing count to a double so that when it is truncated to an int, the for loop will go until the second middle value instead of the first.

## Potential Improvements

There is also a two pointers solution that looks interesting, I may want to look into it in the future; I know there is a two pointers section of this LeetCode training course coming up.
