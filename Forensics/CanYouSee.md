## Description
How about some hide and seek? Download this file [here](https://artifacts.picoctf.net/c_titan/130/unknown.zip).

## Steps to Solve
1. After extracting the zip file, I ran `exiftool` on the image file named `ukn_reality.jpg`
2. This confirmed that this is actually a JPEG, and opening the image didn't really give me anything useful:
![](attachments/Pasted%20image%2020240315163222.png)
3. Running `binwalk` didn't show me any hidden files either
4. I decided to ask my teammate for some help and got reminded about the `steghide` command that can be used to embed hidden data in a file
5. Running the following command `steghide extract -sf ukn_reality.jpg` and entering nothing for the passphrase. I got the following message `wrote extracted data to "flag"`
6. I ran a `cat flag` within the directory but received the following message instead `The flag is not here maybe think in simpler terms. Data that explains data.`
7. This seemed to indicate that I should be paying attention to the metadata of the file, so I once again ran `exiftool` and noticed that the Attribution URL of the file seemed to be a Base64 Hash: `cGljb0NURntNRTc0RDQ3QV9ISUREM05fNmE5ZjVhYzR9Cg==`
8. I inputted this hash into [CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnROUlRjMFJEUTNRVjlJU1VSRU0wNWZObUU1WmpWaFl6UjlDZz09) and after converting from Base64, I got my flag: **picoCTF{ME74D47A_HIDD3N_6a9f5ac4}**