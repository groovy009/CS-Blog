# Isomorphic Strings

## The Problem

Given two strings `s` and `t`, _determine if they are isomorphic_.

Two strings `s` and `t` are isomorphic if the characters in `s` can be replaced to get `t`.

All occurrences of a character must be replaced with another character while preserving the order of characters. No two characters may map to the same character, but a character may map to itself.

## My Solution

```
class Solution {
public:
    bool isIsomorphic(string s, string t) {
        map<char, int> sMap;
        map<char, int> tMap;

        for (int i=0; i<s.length(); i++){
           
            sMap[s[i]]=i+1;
            tMap[t[i]]=i+1;
        
        }

        if(tMap.size() !=sMap.size()){
            return false;
        }
        for(int i=0; i<tMap.size(); i++){
            
            if (tMap[t[i]]!= sMap[s[i]]){
                
                return false;
            }
        }

        return true;


    }
};
```

## Rationale

My solution operates under the assumption that the given strings the same length, which is provided information in the constraints. I first create two maps to hold the letters and the positions of these letters throughout each word. I then loop through each of the given strings, updating the maps as I go.&#x20;

As I update the maps, I set the key to be whichever letter we are currently on in each word, and the value to be the index of that letter plus one. This creates a pattern of indexes that correspond to the different letters in the string.&#x20;

As the maps are created, the repeating keys' (letters') values rewrite themselves to hold the last index where that letter was present.&#x20;

Once the maps have been built, all we have to do it test to ensure they contain matching values for their corresponding keys. First of all, however, if the maps are different lengths, that means there are a different amount of letters in each string, which automatically prevents the strings from being isomorphic.&#x20;

After we check for this, we can loop through each of the maps and make sure the each of the values at the matching key locations are the same. If they are not, that means the word is not isomorphic.

<figure><img src="../../.gitbook/assets/Screenshot 2023-06-27 154959.png" alt=""><figcaption></figcaption></figure>

