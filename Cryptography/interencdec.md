## Description
Can you get the real meaning from this file. Download the file [here](https://artifacts.picoctf.net/c_titan/110/enc_flag).

## Steps to Solve
1. The first step I did was to download the file onto my Kali VM
2. After navigating to the directory the file was in and running a `cat enc_flag` I was given the following hash: `YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6ZzJhMnd6TW1zeWZRPT0nCg==`
3. I ran a `file enc_flag` command to see if I could get any more info from this file but I was only told that it is in `ASCII text`
4. I decided to attempt to identify this hash using the `hash-identifier` command that's built into to Kali linux, however, this did not seem to find any hash
5. I realized that I needed to try to convert this ASCII into human-readable text and decided to try a simple [ASCII-to-text converter](https://www.duplichecker.com/ascii-to-text.php)
6. This resulted in the following binary being shown: `84 104 97 116 32 105 115 32 115 97 109 112 108 101 32 116 101 120 116`, so I knew I was headed in the right direction
7. I decided that instead of just using a binary to text converter, I'd instead use [CyberChef](https://gchq.github.io/CyberChef/)as this would allow me to easily add multiple conversions in a single web-page rather than jumping from one website to the next
8. While I thought this was what I needed to do, I realized that these numbers weren't actually binary at all and instead decimal
9. By running the input with a decimal recipe within CyberChef, I got the following result: `That is sample text`
10. This didn't seem to help me at all and I realized that more needed to be done on my end to solve this challenge