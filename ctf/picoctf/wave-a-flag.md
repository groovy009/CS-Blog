---
description: 10 points
---

# Wave a Flag

![](<../../.gitbook/assets/Screenshot (6).png>)

In order to download the program, I right clicked on the link and copied the link address. Afterwards I used wget and pasted the address, which downloaded the file to my computer.

```
groovy9@Disco:~/ctf/picoPractice$ wget https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm
--2021-10-28 21:22:31--  https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: ‘warm’

warm                          100%[=================================================>]  10.68K  --.-KB/s    in 0.002s

2021-10-28 21:22:31 (5.48 MB/s) - ‘warm’ saved [10936/10936]

groovy9@Disco:~/ctf/picoPractice$
```

I then used chmod to let myself execute the file, and from there getting the flag was very easy.

```
groovy9@Disco:~/ctf/picoPractice$ chmod +x warm
groovy9@Disco:~/ctf/picoPractice$ ./warm
Hello user! Pass me a -h to learn what I can do!
groovy9@Disco:~/ctf/picoPractice$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_f0668f62}
groovy9@Disco:~/ctf/picoPractice$
```

