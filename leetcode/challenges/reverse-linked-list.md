# Reverse Linked List

## The Problem

Given the `head` of a singly linked list, reverse the list, and return _the reversed list_.

## My Solution

```
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        if(!head || !head->next){
            return head;
        }
        
        ListNode *traveller=head;
        ListNode *newNode = new ListNode(head->val);
        
    
        while(traveller->next){
            traveller=traveller->next;
            newNode= new ListNode(traveller->val, newNode);
            
        }

        return newNode;
        
    }
};
```

<figure><img src="../../.gitbook/assets/Screenshot 2023-07-01 163653.png" alt=""><figcaption></figcaption></figure>

## Rationale

For this problem, my first thought was to traverse all the way to the end of the linked list and start reversing from there; however, I wanted to keep in mind my goal to break that habit, so I came up with a solution that would allow me to create the reversed list as I traversed through the given one.

After the necessary edge case checks, I make a new node that starts at the first value of head. This will hold our "previous" value for our new and reversed list. After starting with this value, I iterate through the given list, updating the variable to be a new node which holds the current value we are at in the list, and setting the next node to itself.

By making a new node each time we move through the list and setting its next to the previous value of our newNode variable, as the list is being built, the next we give it will continue to grow in size, until our final newNode creation at the end of the list holds the value at the end of "head", and the next we give it is the entirety of our reversed list up to this point.

## Potential Improvements

The problem with this solution, as you can see by my distribution chart, is that creating a new node each time takes up a lot of memory. To fix this, I want to redo my solution without creating any new nodes.

The tricky part about not creating new nodes, however, is that if I create a new list and initialize it to head, whenever I set that new list's next to whichever previous value is needed, it will break our given list, and all of the values will be lost.

To fix this, I will simply need to create a pointer that points to our next and save that value as we populate our new list. This way, we can update the next of our head each time we move through the list and nothing will be broken :)

## Modified Solution

```
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        if(!head || !head->next){
            return head;
        }
        
        ListNode *traveller=head;
        ListNode *newList = head;
        ListNode *prevNode = nullptr;
        
    
        while(traveller){
            ListNode *realNext = traveller->next;
            newList = traveller;
            newList->next= prevNode;
            prevNode = traveller;
            traveller = realNext;
            
            
        }

        return newList;
        
    }
};
```

<figure><img src="../../.gitbook/assets/Screenshot 2023-07-01 170826.png" alt=""><figcaption></figcaption></figure>
