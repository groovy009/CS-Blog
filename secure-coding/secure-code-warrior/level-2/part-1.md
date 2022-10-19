---
description: LDAP injection
---

# Part 1

## The problem

<figure><img src="../../../.gitbook/assets/Screenshot (68).png" alt=""><figcaption></figcaption></figure>

We are tasked with finding the vulnerable line of code in the program.&#x20;

I will be omitting the specific answers to these questions; however, the vulnerable line of code was embedding unchecked user data into and LDAP request. This can lead to LDAP injection.

For example, you could become a super user on the LDAP servers by simply inputting "\*))%00" The %00 will omit all of the following symbols in the LDAP filter expression, and the expression will be left with ((&(cn=\*)). Thus, granting super user authorization.

## The solution

<figure><img src="../../../.gitbook/assets/Screenshot (69).png" alt=""><figcaption></figcaption></figure>

We must now pick the correct solution for the vulnerable code.

The correct solution must ensure that both the superUserLogin and the superUserPassword are valid.
