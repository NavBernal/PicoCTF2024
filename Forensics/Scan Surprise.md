## Description
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead? You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_atlas/15/challenge.zip)

Additional details will be available after launching your challenge instance.
## Steps to Solve
1. I first downloaded the file then launched the instance on the pico website
2. This revealed to me the following details that were hidden before:
	- The same files are accessible via SSH here: `ssh -p 49480 ctf-player@atlas.picoctf.net` Using the password `1db87a14`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!
3. After extracting the zip file, I cd'd into the 'drop-in' folder and found that there was a file named `flag.png`
4. After running a `file flag.png` command, I received the following details: `PNG image data, 99 x 99, 1-bit colormap, non-interlaced`
5. This didn't tell me much, so I decided to open the image using the GUI only to find a simple QR code
6. As I was hesitant to scan the code, I decided to run some extra forensic commands on the image to see if I could get any more useful information
7. I first tried running `exiftool`, but this didn't seem to give me any useful information outside of confirming that this is a png file
8. I then ran `binwalk` on the image, but once again it didn't give me any useful info
9. I then decided to finally scan the qr code using my phone, and what do you know, I got the flag
10. After feeling like an idiot, I was happy to have the following flag: **picoCTF{p33k_@_b00_19eccd10}**