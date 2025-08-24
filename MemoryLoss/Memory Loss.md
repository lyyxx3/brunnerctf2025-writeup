# Forensic Challenge: Memory Loss
<img width="457" height="473" alt="image" src="https://github.com/user-attachments/assets/1943fcff-04f4-423c-be1a-8b0133ae8c37" />

<br>
<br>

From the challenge description, it is hinted that we need to find a picture, so perhaps `.png`, `.jpeg`, `.jpg`.
<br>
So, launching Volatility3 and do a File Scan and start grepping for image files.
<br>
<br>
`python3 vol.py -f memoryloss.dmp windows.filescan.FileScan | grep .png`
<br>
<br>
<img width="1269" height="271" alt="image" src="https://github.com/user-attachments/assets/dfd74978-03e5-4af9-8197-60b9947de330" />
<br>
We got a few hits already, lets try dumping them out and see.
<br>
<br>
`python3 vol.py -f memoryloss.dmp windows.dumpfiles.DumpFiles --virtaddr 0xb207c3ab6c40`
<br>
<br>
Aaand theres the flag.
<img width="1604" height="1202" alt="image" src="https://github.com/user-attachments/assets/32d155fe-e30d-4063-ab60-44fb0987e324" />
<br>
<br>
**Flag:** brunner{0h_my_84d_17_w45_ju57_1n_my_m3m0ry}



