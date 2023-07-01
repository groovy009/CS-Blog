---
description: Another classic
---

# Is Subsequence

## The Problem

Given two strings `s` and `t`, return `true` _if_ `s` _is a **subsequence** of_ `t`_, or_ `false` _otherwise_.

A **subsequence** of a string is a new string that is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (i.e., `"ace"` is a subsequence of `"abcde"` while `"aec"` is not).

## My Solution

```
class Solution {
public:
    bool isSubsequence(string s, string t) {
      int subIndex=0;

      for(int i=0; i<t.length() && subIndex<s.length();i++){
          if(t[i]==s[subIndex]){
              subIndex++;
          }
      }
      return (subIndex ==s.length());
    }
};
```

## Rationale

This is another common problem given to computer science students. The trick is to have to indexes, one for the substring, and one for the full string. As we loop through the full string, whenever there is a match we can increment the index of the subsequence and the full string. Otherwise, we only increment the index of the full string to try and look for matches.&#x20;

After the loop has completed, if the substring index is at the last character in the substring, that means there was a match for every letter in order, so a subsequence is present.

<figure><img src="../../.gitbook/assets/Screenshot 2023-06-27 173246.png" alt=""><figcaption></figcaption></figure>

## Potential Improvements

While I am not talking about improvements for my solution to this problem specifically, I will be reviewing the first time I saw this problem and the mindset I went in with.

When I first saw this problem years ago, my first thought was to create a dictionary that would hold each letter and its corresponding position in the full string. After this was created, I would check each letter in the substring and make sure they were present in the dictionary. If they were, I would then ensure the order was from least valued in the dictionary to most valued.&#x20;

This is not the fastest way to complete this problem, which I learned. Many times when I look at a problem, my first thought it to run through the entire first parameter once and use a data structure to create a key that I can check with the second parameter later. I want to get better at running through the first parameter and checking at the same time to streamline my code.
