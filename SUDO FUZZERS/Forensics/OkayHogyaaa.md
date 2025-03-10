# Challenge Name - Okayhogyaaa
# Author: g0kbur0 
# Writeup written by: Noor Ul Hassan
### Category: Forensics
### Difficulty: Medium

## Approach & Solution
Download the pcap file and open it  

![.pcap file opened in wireshark](./images/ss1.png)  

Now check the ICMP Header and then data:  

![.pcap file opened in wireshark](./images/ss2.png)  

Copy this as value and then paste it in dcode.fr (This is an ASCII) and decode it.  

![decode.fr](./images/ss3.png)  

As you can see, there is a Google Drive link. Copy this and paste it into your browser. Go to the SUDO FUZZERS folder and analyze it.  

![drive](./images/ss4.png)  

Open the ReadmeMUST.txt  

![ReadmeMUST.txt](./images/ss5.png)  

This says to combine all of the files, but which files? We will see later. Now, download the DownloadME.zip as it seems suspicious.  
After the download is complete, extract the file.  

![Extracting DownloadME.zip](./images/ss6.png)  

After extraction, you will see four more .zip files named as part0, part1, and so on. Here, we will use the hint of combining all the files in one folder. Extract all of them and then place them in one folder.  

![Extracting parts](./images/ss7.png)  

Now, I have combined all of them in a separate folder.  

![Combining them](./images/ss8.png)  

As you can see from the files, this is a Kali VM machine and now we simply need to open it in VMware.  

![Opening VM](./images/ss9.png)  

Power on the machine  

![Power on the VM](./images/ss10.png)  

The machine will ask for a snapshot file to open the VM with the extension .vmsn  

![finding snapshot](./images/ss11.png)  

Click on browse, select type as **All files**, and choose **"kali-linux-2024.3-vmware-amd64.vmxf"**  

![browsing snapshot](./images/ss12.png)  

Your VM will load and will ask for the username and password. By default, the username and password of the Kali machine are `kali` and `kali`, and this works in this case.  

![kali](./images/ss13.png)  

You will now see a lot of folders on the *Desktop* containing false flags:  

![kali Desktop](./images/ss14.png)  

Now go to the *home* directory and press *CTRL+H*. This will show all the hidden files. Click on the *bash_history* file.  

![bash history](./images/ss15.png)  

In the bash history file, we found that the folders **flagyahanhe169** and **flagyahanhe239** were visited by the previous user.  

![bash history](./images/ss16.png)  

Now, when we visit **flagyahanhe239**, we find one encrypted folder and one script to unlock that folder.  

![flagyahanhe239](./images/ss17.png)  

Now, when we try to open the script, it says we do not have permission. So open the terminal here and use the following command:  

```bash
sudo chmod +x unlock_folder.sh
# Command used to make the script executable

Now run the following command:

    sudo nano unlock_folder.sh

this will open the script in the editor and now you can see the content of the file:

![script](./images/ss18.png)  

Now from the code we know that the script need a key and key.txt file which contains the key in the same directory as the script. So we wil create the key.txt file

![key.txt](./images/ss19.png)

Now the only thing we need is the key. Now where we will find the key?? Now there are two ways one is in the kali system and other is in the google drive form where we downloaded the kali machine. I will go with 1st one but will also tell you about the 2nd one.

Go to the home directory and find the .zsh_history. Analyze the file there you will find the cr7.jpg file and the author using exiftool pushed a comment to that picture. You will find the picture in the drive and use exiftool to find the comment but we can also find it here in the .zsh_history.

![zsh_history](./images/ss20.png)

Now paste this key in the key.txt file and run the script it will unlock the folder.


![](./images/ss21.png)

![](./images/ss22.png)

Now the folder has unlocked.

![](./images/ss23.png)

Now in the folder in the txt file you will find the flag.

![Flag](./images/ss24.png)







