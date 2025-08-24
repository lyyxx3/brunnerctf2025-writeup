# Mobile Challenge: Bake Down
<img width="449" height="619" alt="image" src="https://github.com/user-attachments/assets/398fc786-8c6c-443e-a5f8-01206de13b1b" />
<br>
<br>

## **Step 1: Disassemble the APK**
You can use `apktool` for this but im gonna use jadx-gui,
<br>
apktool cmd: `apktool d <apkfile>`
<br>
<br>
Open jadx, navigate to `resources.arsc->res->values->strings.xml`
<br>
<br>
<img width="326" height="301" alt="image" src="https://github.com/user-attachments/assets/d9117636-0d6f-4f81-86d7-d3758cf88399" />
<br>
Scrolling down, u shud see the first part of the flag,
<img width="991" height="97" alt="image" src="https://github.com/user-attachments/assets/0134d425-4a5c-44d5-8491-a9100f86e50f" />
<br>
**First Part:** `brunner{Th1s_Sh0uld_B3_Th3_`

## **Step 2: Run the APK on an Emulator**
im using Android Studio for this. 
- Open the apk file in Android Studio.
- Since the apk runs on at least API version 30, add a new device in Device Manager tht has at least API 30.
- Run the device, drag the apk into the device interface.
- Once installed, open the app.
<img width="399" height="896" alt="image" src="https://github.com/user-attachments/assets/5450aaa2-2cde-40af-ac36-e96fd593c494" />
<br>
You should get this interface, then click Next.
<br>
<br>
<img width="399" height="478" alt="image" src="https://github.com/user-attachments/assets/c6997583-6b36-4690-8e94-fe96facea457" />
<br>

**Second Part:** B3g1nn1ng_0f_Y0ur_M0b1l3_3xp3r13nc3}

<br>
<br>

**Flag:** brunner{Th1s_Sh0uld_B3_Th3_B3g1nn1ng_0f_Y0ur_M0b1l3_3xp3r13nc3}

