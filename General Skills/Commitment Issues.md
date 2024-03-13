## Description
I accidentally wrote the flag down. Good thing I deleted it! You download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/138/challenge.zip)

## Steps to Solve
1. I downloaded and extracted the `challenge.zip` file inside my Kali VM and began poking around
2. After running a `ls -a` command on the drop-in folder that was extracted from the zip file, I found that there was a hidden .git folder
3. I first began poking around this folder and took a look at the logs folder where I then navigated to `refs/heads` and found the master branch
4. After running `cat master`, I was met with the following: ![[Pasted image 20240312231817.png]]
5. This indicated to me that there should be an initial commit that contains the created flag before it was removed
6. I couldn't remember how to display a past git commit, so I decided to look it up and found the following [git documentation](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)
7. While this page didn't show me how to show a past command, it did reveal to me that an easier way to view git logs is by simply running the `git log` command which displayed the following: 
![[Pasted image 20240312232532.png]]
8. This presented the logs in a more readable format and made it clear the exact commit hash that I needed in order to display the flag
9. After looking around the web some more, I came across the following [stack overflow post](https://stackoverflow.com/questions/7663451/view-a-specific-git-commit) that stated all I needed was the simple command `git show <revhash>`
10. After running this in my Kali machine, I was presented with the following that gave me my flag **picoCTF{s@n1t1z3_c785c319}**:
![[Pasted image 20240312232904.png]]