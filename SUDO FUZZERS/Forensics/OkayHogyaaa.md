# Challenge Name - Okayhogyaaa
# Author: g0kbur0 
### Category: Forensics
### Difficulty: Medium

## Approach & Solution
Download the pcap file and open it

![.pcap file opened in wireshark](./images/ss1.png)

Now check the ICMP Header and then data:

![.pcap file opened in wireshark](./images/ss2.png)

Copy this as value and then paste in dcode.fr (This is an ASCII) and decode it.

![decode.fr](./images/ss3.png)

as you can see there is google drive link copy this and paste in your browser. Go to the SUDO FUZZERS folder and analyze it.

![drive](./images/ss4.png)

Open the ReadmeMUST.txt

![ReadmeMUST.txt](./images/ss5.png)

this says to combine all of the files but which files? we will see later. Now dowload the DownloadME.zip as it seems sus.
After download is complete extract the file.

![Extracting DownloadME.zip](./images/ss6.png)

After the extraction you will see four more .zip file named as part0,part1 and so on. Here we will use the hint of comnining all the files in one folder. Extract all of them and then paste in one folder.

![Extracting parts](./images/ss7.png)

Now I have combined all of them in a seprate folder.

![Combining them](./images/ss8.png)

As you can see from the files this is a kali vm machine and now we simply need to open it in VMware.

![Opening VM](ss9.png)

Power on the machine

![Power on the VM](ss10.png)

the machine will ask for a snapshot file to open the VM with extension .vmsn

![findin snapshot](ss11.png)

```bash
# Command used
