---
description: The classic
---

# Running Sum of 1d Array

## The problem

Given an array `nums`. We define a running sum of an array as `runningSum[i] = sum(nums[0]…nums[i])`.

Return the running sum of `nums`.

## My solution

```
class Solution {
public:
    vector<int> runningSum(vector<int>& nums) {
        vector<int> runSum;
        int sum=0;
        for(int i=0; i<nums.size(); i++){
            sum += nums[i];
            runSum.push_back(sum);
        }

        return runSum;
        
    }
};
```

## Rationale

This is one of the most basic problems thrown around for computer science beginners. Solving the problem requires a basic understanding of loops, arrays, and arithmetic operations.&#x20;

When coding my solution, I chose to populate my runSum array as I calculated the sums so that my code would work using only one for loop and run in O(n) time.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2023-06-26 152112.png" alt=""><figcaption></figcaption></figure>

## Roadblocks and Potential Improvements

This is a problem many people have already completed, including myself. So, I did not run into any roadblocks in coming up with my solution.

To improve, I am sure I could use a hashmap to optimize the solution further; however, I want to spend my time working on new and more challenging problems instead of maximizing my code efficiency on this one.
