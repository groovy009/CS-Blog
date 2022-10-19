---
description: Insecure Randomness
---

# Part 2

## Find the vulnerability

We must first find the type of vulnerability present in the code.

<figure><img src="../../../.gitbook/assets/Screenshot (70).png" alt=""><figcaption></figcaption></figure>

Much like in Level 1, std::srand is considered insecure randomness, especially without setting a seed.&#x20;

## Find the solution

We are now tasked with finding the best solution to this insecure randomness.

<figure><img src="../../../.gitbook/assets/Screenshot (71).png" alt=""><figcaption></figcaption></figure>

In this case, there are two options that seem enticing. One is in the picture above; setting the random seed to nullptr allows for the program to generate new random values each time you run the program.

However, while this is acceptable for school projects, in the real world this is still very insecure. There is a better option that uses a much safer random library introduced in C++11.
