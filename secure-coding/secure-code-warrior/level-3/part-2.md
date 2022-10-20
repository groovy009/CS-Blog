---
description: Insecure Cryptography- exposed key
---

# Part 2

## Locate the vulnerability

<figure><img src="../../../.gitbook/assets/Screenshot (77).png" alt=""><figcaption></figcaption></figure>

In the code above, the key is not only a global variable, it is also stored in plain text. This is a big security risk as one could easily find the key value by reverse engineering.

## Find the solution

<figure><img src="../../../.gitbook/assets/Screenshot (78).png" alt=""><figcaption></figcaption></figure>

Solution 1 turns the character pointer into a string variable, but the change in data types does not solve the issue; the key is still being stored as plain text.

Solution 3 changes the global variable to a variable declared in the main function; but the key is still stored as plain text.

Solution 4 stores the key in plain text, but in reverse. It then calls a reverse function later in main.&#x20;

In order to properly secure the key, it must be encrypted when stored and then decrypted before use.
