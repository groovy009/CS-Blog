---
description: Sensitive data storage
---

# Part 1

## Find the Vulnerability

You get the gist by now; it's time to find that vulnerability!

<figure><img src="../../../.gitbook/assets/Screenshot (74).png" alt=""><figcaption></figcaption></figure>

In this case, no encryption was used to store the RSA private key information. It is not enough to just save the data on the server side.&#x20;

## Find the Solution

<figure><img src="../../../.gitbook/assets/Screenshot (75).png" alt=""><figcaption></figcaption></figure>

In order to properly encrypt the RSA private key, it is necessary to use the Advanced Encryption Standard algorithm with a 256-bit length key.
