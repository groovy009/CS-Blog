# Find Pivot Index

## Problem

Given an array of integers `nums`, calculate the **pivot index** of this array.

The **pivot index** is the index where the sum of all the numbers **strictly** to the left of the index is equal to the sum of all the numbers **strictly** to the index's right.

If the index is on the left edge of the array, then the left sum is `0` because there are no elements to the left. This also applies to the right edge of the array.

Return _the **leftmost pivot index**_. If no such index exists, return `-1`.

## My Solution

```
class Solution {
public:
    int pivotIndex(vector<int>& nums) {
        int sum=0;

        //calculate the total sum of the array
        for(int i=0; i<nums.size(); i++){
            sum+=nums[i];
        }


        //for each index, calculate the target sum
        int runningSum= 0;
        for(int index=0; index< nums.size(); index++){
            double targetSum = (double)(sum-nums[index])/2;
            
            if(index!=0){
                runningSum+=(nums[index-1]);
            }

            if(runningSum==targetSum){
                return index;
            }
        }
        return -1;
        
    }
};
```

<figure><img src="../../.gitbook/assets/Screenshot 2023-06-26 152047 (1).png" alt=""><figcaption></figcaption></figure>

## Rationale

For this problem, I first thought about the conditions necessary to find a pivot point, which led me to the crux of my solution: the targetSum variable.&#x20;

In order to find a pivot point, we need both sides of the index we have selected to have an equal sum. Since we know both sides  must be equal, adding both sides together will give us the same result as multiplying one side by 2.&#x20;

I use this fact to calculate the targetSum variable without having to loop through each side of the index to count each sum. Assuming each side is equal, we can simply represent our target sum as the sum of the entire list(sum) divided by 2. Since our index is not included in the sum for either side, all we have to do is subtract the current index value from the target sum as well.

So, targetSum = (totalSum/2) - value at current index.&#x20;

All that's left is to have a variable for our runningSum of the left side of the index. Update and compare it's value to target sum each time we move our index, and we are done!

## Roadblocks&#x20;

A slight issue I came across at first was rounding when computing the targetSum. Without casting sum and nums\[index] to a double before dividing by 2, C++ rounds the computation to an integer, which will cause the code to find incorrect pivot indexes.&#x20;

## Potential Improvements

Upon completing my solution, I looked at the highest upvoted solution posted on LeetCode and found my solution was exactly the same aside from formatting, variable names, etc. However, while I update my runningSum as a seperate statement within my for loop, the forum solution updates their sum within the parameters of the for loop itself (; leftSum+= sum\[i++]).

This is something I did not know was possible, and seemed like it would streamline my code; so, I tried moving my runningSum updates to the same spot.&#x20;

It worked, and improved the runtime of my code by 7 ms. Interestingly however, it worsened the memory usage of the code as well.

<figure><img src="../../.gitbook/assets/Screenshot 2023-06-26 160705.png" alt=""><figcaption></figcaption></figure>
