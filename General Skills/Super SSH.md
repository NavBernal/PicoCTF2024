1. I opened up a Kali terminal and first inputted the following command: `ssh ctf-player@titan.picoctf.net`
2. After being denied access, I realized I needed to specify the port they wanted me to ssh into during the initial command
3. After searching up the proper syntax for defining a port in the ssh command, I tried the following instead: `ssh -p 49566 ctf-player@titan.picoctf.net`
4. After typing yes to continue the session as well as entering the provided password, I was able to get the following flag: **picoCTF{s3cur3_c0nn3ct10n_45a48857}**
