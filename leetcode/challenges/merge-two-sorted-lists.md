# Merge Two Sorted Lists

## The Problem

You are given the heads of two sorted linked lists `list1` and `list2`.

Merge the two lists in a one **sorted** list. The list should be made by splicing together the nodes of the first two lists.

Return _the head of the merged linked list_.

## My solution

```
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) {
        if(!list1) return list2;
        if (!list2) return list1;
        ListNode *sortedList = list1;
        if(list1->val > list2->val){
            sortedList = list2;
            list2 = list2->next;
        }
        else{
            sortedList=list1;
            list1 = list1->next;
        }
        ListNode *traveller= sortedList;

        while(list1 && list2){
            if(list1->val > list2->val){
                traveller->next=list2;
                list2 = list2->next;
            }
            else{
                traveller->next= list1;
                list1 = list1->next;
            }
            traveller = traveller->next;

        }

        if(!list1){
            while(list2){
                traveller->next = list2;
                traveller=traveller->next;
                list2=list2->next;
            }
        }
        else{
            while(list1){
                traveller->next = list1;
                traveller=traveller->next;
                list1=list1->next;
            }
        }

        return sortedList;
        
    }
};
```

<figure><img src="../../.gitbook/assets/Screenshot 2023-06-29 151713.png" alt=""><figcaption></figcaption></figure>

## Rationale

My solution for this problem was a very straightforward, iterative approach. I first make sure the two lists are populated, if one is not, I return the populated list. After this check, I see which list holds the smallest value at first, and create a new list that starts with that value. Then, much like the Is Subsequence solution, I compare values as I iterate through each list, only incrementing on the list with the smallest value, which I also add to my sortedList.

In the future, I would like to try to implement a recursive solution, as I know those are possible for this problem.
