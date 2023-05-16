---
description: Anadiagrams? Dianagrams.
---

# Day 2: General Design and Starting Class Diagrams

## General design

In terms of the general structure I have planned for my app, I feel as though using the MVC (Model View Controller) pattern makes the most sense for the smaller scale game I am going for.

<figure><img src="../../.gitbook/assets/model-view-controller-light-blue.png" alt=""><figcaption></figcaption></figure>

The true crux of the backend, however, will be an unsorted list/hashmap containing all words and their corresponding sorted key. The key will be all of the letters in a word sorted in alphabetical order (the words reem and mere would share the same key of "eemr").&#x20;

By using this HashMap method, I can easily check if someone has found an anagram by matching the sorted key of their response with that of the given letters. To ensure their respose is a real word, all I need to do is additionally check if it is contained in a word list of all words. This will be accomplished as input validation in the view layer of my application.

## Diagrams

I have decided to stick with Draw.io for my diagrams, as it is what I am used to. As I am not sure how to use swift or any UI tools this early on, I will be sticking to planning out and diagraming the model and controller portions of my app over the next few days, and save the view layer for the future. Today, I knocked out the class diagram for WordBank.

All of these diagrams are subject to change and very likely will throughout this process, these are just my initial ideas.

### Word Bank

<figure><img src="../../.gitbook/assets/Untitled Diagram-Page-2.drawio.png" alt=""><figcaption></figcaption></figure>

#### wordList

The WordBank class is a model that contains an unsorted list with all of the words in a word list as well as a key that corresponds to them.

#### Constructor

The WordBank class has a constructor that initializes this unsorted list (named wordList) with all of the words in a given word list. The word list I used for my C++ skeleton code is below, but I may change the word list in the future.

{% file src="../../.gitbook/assets/wordlist.txt" %}

In order to streamline the initialization process, the constructor takes in a minimum word size that will be chosen by the viewer in the view layer, sent to the control layer in main, and eventually passed in the constructor to update the word bank in models. This minimum word size allows the constructor to only add the words of the user's selected size, and avoids the excess.

#### getRandomLetters

Finally, the WordBank class has a public get method that returns a scrambled set of letters from one of the entries in the wordList unsorted list. These letters would be what the player uses to create as many words as they can. The letters returned will be sure to contain at least 5 anagrams; i.e., have 5 other words that share its same key (exist in the same bucket in the HashMap).
