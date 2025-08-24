# Forensic Challenge: VeryCheap
<img width="774" height="540" alt="image" src="https://github.com/user-attachments/assets/912e9f8f-73dc-4b69-8981-2ed8b9a6fc4e" />
<br>
<br>

## **Step 1: Analyzing the Disk Image**
First of all, checking all the typical folders like Desktop, Documents and Downloads using Autopsy.
<br>

### **Findings from Desktop**
File Path: `/img_VeryCheap.E01/vol_vol6/Users/Joe/Desktop`
<br>
- `test_container_password.txt`: Password for my test container is "brunsviger".
<img width="665" height="572" alt="image" src="https://github.com/user-attachments/assets/b90ec24d-9835-4998-bf29-eae9ed835129" />
<br>
<br>

### **Findings from Documents**
File Path: `/img_VeryCheap.E01/vol_vol6/Users/Joe/Documents`
<br>
- Some pdf files (After extracting them, seems to be just normal pdfs)
- test.hc (A VeraCrypt Container)
<img width="615" height="391" alt="image" src="https://github.com/user-attachments/assets/b57711d1-5d23-4dc5-975c-bce44b50178e" />
<br>
<br>

### **Findings from Downloads**
File Path: `/img_VeryCheap.E01/vol_vol6/Users/Joe/Downloads`
<br>
- VeraCrypt.exe
- LibreOffice.msi
<img width="821" height="352" alt="image" src="https://github.com/user-attachments/assets/8c1d18d1-c75b-4aa2-80ef-1c7ff42b7557" />
<br>
<br>
Checking the Web History, we can see that they are searching for a program to hide files, and seems like they found VeraCrypt.
<img width="1467" height="535" alt="image" src="https://github.com/user-attachments/assets/00c36f10-e053-4cf9-ab00-405aa7b0cf23" />

<br>
<br>

## **Step 2: Cracking the First VeraCrypt Container**
Now go and extract `test.hc` from the Documents folder, and use VeraCrypt to mount and open it. <br>
- Select the `test.hc` file.
- Choose a disk, any one is fine.
- Click Mount.
- Enter `brunsviger` as password.
<br>
Open it up and all we get is a text file. Seems like this is a test container, it doesnt contain the flag.
<img width="1319" height="235" alt="image" src="https://github.com/user-attachments/assets/82083d60-9b1a-4dc9-b852-5a624170f963" />
<br>
So we can speculate there is Another Container somewhere and also a Password for that hidden container.
<br>
<br>

## **Step 3: Finding the Second VeraCrypt Container**
Going back to the Web History, scrolling further down, we found more info about the location of the second container.
<img width="1450" height="528" alt="image" src="https://github.com/user-attachments/assets/08854e14-1851-4028-a457-102e1c7262c0" />
Findings:
- They used VeraCrypt CLI, which means we can check their command history.
- Searches about Keyfiles, indicates the second container might be also encrypted with a Keyfile.
- Things we need to find: Second Container, Keyfile, Password
<br>
<br>

### **Checking Command History**
File Path: `/img_VeryCheap.E01/vol_vol6/Users/Joe/AppData/Roaming/Microsoft/Windows/PowerShell/PSReadLine/ConsoleHost_history.txt`
<img width="1424" height="299" alt="image" src="https://github.com/user-attachments/assets/6aae8d9e-514d-4eaf-8ded-666dd28dc74b" />
Findings:
- /v 'C:\Program Files\7-Zip\7z.dll' - Container location (disguised as 7z.dll)
- /p "VeryCheapAndDeliciousBrunnerForAll" - Hidden volume password
- /k ".\Pictures\VeryCheapBrunner.png" - Keyfile (the PNG image)
<br>
Good, we got the location of everything we need, now just go to their respective folder paths to extract them.
<br>
Respective File Paths:
- /img_VeryCheap.E01/vol_vol6/Program Files/7-Zip/7z.dll
- /img_VeryCheap.E01/vol_vol6/Users/Joe/Pictures/VeryCheapBrunner.png
<br>
<br>

## **Step 4: Cracking the Second VeraCrypt Container**
<img width="1273" height="769" alt="image" src="https://github.com/user-attachments/assets/dcb2698b-7ba3-465d-88e7-625544800d9c" />
This container doesnt contain the flag either, but we did get some hints. <br>
Findings:
- This probably means we need a different password to mount this same container.
- Something about sticky notes, maybe we can find some info there.

<br>
<br>












