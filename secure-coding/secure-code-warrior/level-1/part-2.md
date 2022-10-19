---
description: Insecure Cryptography (200 points)
---

# Part 2

The electrical company was using std::rand() to generate their random passwords; however this function is very insecure; especially without setting a seed (which they did not do).&#x20;

To fix this, they should use a random function introduced in C++11 to more securely generate random passwords.
