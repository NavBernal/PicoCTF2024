## Description
People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate. You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_rhea/22/challenge.zip)

## Steps to Solve
1. After downloading and extracting the zip file on my Kali VM, I first navigating through the file to find my checksum file labeled `checksum.txt`
2. I took the text that was inside of this file and ran it through `hash-identifier` which labeled this as being a SHA256 hash
3. I then attempted to verify all of the files located in the `files` folder to see if any of their checksums matched with the one I currently had
4. I wanted to find a way to do this for all the files within the folder using a single command, so I came across this [askubunute post](https://askubuntu.com/questions/907953/how-can-i-recursively-list-md5sum-of-all-the-files-in-a-directory-and-its-subdir) that showed me how to do just that
5. Using the following command `find -type f -exec sha256sum '{}' \; > sha256sums.txt` I was able to generate a text file containing checksums for every single file within that folder
6. I then copied the checksum provided to us within `checksum.txt`, opened the newly generated text file from the last step, and ran `Ctrl+F` to find the file that matched which ended up being file name `2cdcb2de`
7. I then ran the following command to decrypt the file `./decrypt.sh files/2cdcb2de`, however, I kept being met with the following error message `Error: '2cdcb2de' is not a valid file. Look inside the 'files' folder with 'ls -R'!`
8. I realized that the file must've gotten corrupted at some point since I decided to copy and past it into the previous `drop-in` directory for whatever reason
9. After trying to delete and redownload the zip file multiple times to no avail, I decided to just follow the SSH instructions provided when launching the instance on pico and after re-running the decrypt command I got the following flag: **picoCTF{trust_but_verify_2cdcb2de}**