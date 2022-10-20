---
description: Function level access control
---

# Part 3

## Identify the type of vulnerability

<figure><img src="../../../.gitbook/assets/Screenshot (79).png" alt=""><figcaption></figcaption></figure>

In the picture above, the vulnerability is the permanent read/write functions. These can cause a DoS issue as well as allow the possibility of faulty data being inserted into the database.&#x20;

## Find the solution

<figure><img src="../../../.gitbook/assets/Screenshot (80).png" alt=""><figcaption></figcaption></figure>

The solution is to load and save the file at the appropriate times. The memory of the computers serves as the buffer.&#x20;
