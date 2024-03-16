## Description
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file? Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/98/flag2of2-final.pdf).

## Steps to Solve
1. I first downloaded the file to my Kali VM and opened the pdf only to find a blank page with only the following text: `1n_pn9_&_pdf_1f991f77}`
2. This seemed to look somewhat like a flag to me, so I decided to examine the file using `exiftool`
3. When looking at the metadata, I as able to see that despite the file ending in .pdf, it was actually a PNG file type that was created using GIMP
4. I decided to rename the file to contain .png at the end and when opening the image, I got the following:
![](attachments/Pasted%20image%2020240315215922.png)
5. Seeing as how this looked like the start of a flag, I decided to try combining this with the text I got from the file when it was a pdf earlier which resulted in **picoCTF{f1u3n7_1n_pn9_&_pdf_1f991f77}**
6. This ended up being the correct flag!