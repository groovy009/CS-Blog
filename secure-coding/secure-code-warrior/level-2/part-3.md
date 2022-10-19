---
description: Denial of service
---

# Part 3

## Find the vulnerability&#x20;

We must first select the line of code where the uncaught error handling is present.

<figure><img src="../../../.gitbook/assets/Screenshot (72).png" alt=""><figcaption></figcaption></figure>

The issue here is improperly checking for input parameters. In this case, it could potentially result in a division by zero, causing undefined behavior.

## Find the solution

We must now decide the correct solution for the problem.

<figure><img src="../../../.gitbook/assets/Screenshot (73).png" alt=""><figcaption></figcaption></figure>

To fix this undefined behavior, all one has to do is implement the proper checks that ensure the values can never be 0, and return an error if they are.
