# Challenge Name - Okayhogyaaa
# Author: g0kbur0 
### Category: Forensics
### Difficulty: Medium

## Approach & Solution
1. **Step 1:** Download the pcap file and open it
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



```bash
# Command used
