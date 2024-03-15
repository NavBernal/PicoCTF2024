## Description
What was I last working on? I remember writing a note to help me remember... You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/162/challenge.zip)

## Steps to Solve
1. I first downloaded then extracted the file on my Kali VM and was able to find a .git file inside, indicating that I'd have to be looking through past commits again to find the flag
2. By running a simple `git log` command, I was able to find the following flag: **picoCTF{t1m3m@ch1n3_e8c98b3a}**