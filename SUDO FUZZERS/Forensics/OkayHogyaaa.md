# Challenge Name: Okayhogyaaa
**Author**: g0kbur0  
**Writeup written by**: Noor Ul Hassan  
**Category**: Forensics  
**Difficulty**: Medium

---

## Approach & Solution

1. **Download the pcap file and open it in Wireshark**  
   Open the provided `.pcap` file using Wireshark and inspect the captured packets.  
   ![PCAP File Opened in Wireshark](./images/ss1.png)

2. **Analyze ICMP Header and Data**  
   Check the ICMP Header and the data.  
   ![ICMP Data](./images/ss2.png)

3. **Decode the Data**  
   Copy the decoded value from the ICMP packet and paste it into [dcode.fr](https://www.dcode.fr/), as the data is in ASCII format.  
   ![Decoding with dcode.fr](./images/ss3.png)  
   After decoding, you will find a Google Drive link. Copy this link and paste it into your browser.

4. **Access the Google Drive**  
   Go to the "SUDO FUZZERS" folder on Google Drive and analyze its contents.  
   ![Google Drive Folder](./images/ss4.png)

5. **Open the `ReadmeMUST.txt`**  
   Inside the folder, open the `ReadmeMUST.txt`. It instructs you to combine files, but it doesn’t specify which files to combine. We'll address that later.  
   ![ReadmeMUST.txt](./images/ss5.png)

6. **Download and Extract `DownloadME.zip`**  
   Download the suspicious file `DownloadME.zip` and extract its contents.  
   ![Extracting DownloadME.zip](./images/ss6.png)

7. **Extract the Part Files**  
   After extraction, you will see four `.zip` files named `part0`, `part1`, and so on. Use the hint from the `ReadmeMUST.txt` to combine all of them into one folder.  
   ![Extracting Parts](./images/ss7.png)  
   Combine and place them into a single folder for further analysis.  
   ![Combining Parts](./images/ss8.png)

8. **Open the Kali VM**  
   The files extracted seem to be related to a Kali VM machine. Open it in VMware.  
   ![Opening VM](./images/ss9.png)  
   Power on the VM.  
   ![Power on VM](./images/ss10.png)

9. **Find the Snapshot File**  
   The VM will ask for a snapshot file with the `.vmsn` extension. Browse and select the file `kali-linux-2024.3-vmware-amd64.vmxf`.  
   ![Finding Snapshot](./images/ss11.png)  
   ![Browsing Snapshot](./images/ss12.png)

10. **Login to the Kali VM**  
    The VM will prompt for a username and password. Use the default credentials:  
    - Username: `kali`  
    - Password: `kali`  
    ![Kali Login](./images/ss13.png)

11. **Explore the Kali Desktop**  
    Upon login, you will see many folders on the desktop, which contain false flags.  
    ![Kali Desktop](./images/ss14.png)

12. **Check Hidden Files**  
    Go to the *home* directory and press `CTRL+H` to reveal hidden files. Open the `bash_history` file.  
    ![bash_history](./images/ss15.png)

13. **Analyze the bash_history**  
    In the `bash_history`, you will find that the folders `flagyahanhe169` and `flagyahanhe239` were visited by the previous user.  
    ![bash_history](./images/ss16.png)

14. **Access the Folder `flagyahanhe239`**  
    In the folder `flagyahanhe239`, there is an encrypted folder and a script to unlock it.  
    ![flagyahanhe239](./images/ss17.png)

15. **Make the Script Executable**  
    The script cannot be opened directly due to permission issues. Use the following commands in the terminal to make it executable:

    ```bash
    sudo chmod +x unlock_folder.sh
    sudo nano unlock_folder.sh
    ```

    This will open the script in the editor.  
    ![Script](./images/ss18.png)

16. **Create the Key File**  
    The script requires a key, which should be stored in a `key.txt` file in the same directory as the script.  
    ![key.txt](./images/ss19.png)

17. **Find the Key**  
    There are two ways to find the key:
    - **Option 1**: Check the `.zsh_history` file on the Kali system for the key.
    - **Option 2**: Use the metadata from the `cr7.jpg` image on the Google Drive using [ExifTool](https://exiftool.org/) to find the comment with the key.

    We will go with **Option 1**, but both methods should lead to the same key.  
    ![zsh_history](./images/ss20.png)

18. **Run the Script to Unlock the Folder**  
    After obtaining the key, create the `key.txt` file, place the key in it, and run the script to unlock the folder.  
    ![Unlocking Folder](./images/ss21.png)  
    ![Unlocked Folder](./images/ss22.png)

19. **Extract the Flag**  
    In the unlocked folder, you will find the flag inside a text file.  
    ![Flag](./images/ss24.png)

---

## Conclusion

You have successfully completed the challenge by decoding the ICMP data, analyzing the Google Drive contents, extracting the Kali VM, and using the correct key to unlock the folder. The final flag is now obtained.

