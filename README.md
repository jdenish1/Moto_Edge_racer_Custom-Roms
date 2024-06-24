# Motorola Edge 5G, codename racer, Custom Roms

![Motorola Edge 5G XT2063-2](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/blob/main/images/Motorola%20Edge%205G%20Collage%20-%201st%20Draft.png "Motorola Edge 5G XT2063-2")

***

Custom roms and how to install them on a Motorola Edge 5G #XT2063-2 cell phone. 

***

<h1>Phone Specs:</h1>

   - **Released**
     - May 2020
   - **SOC** 
     - Qualcomm SM7250
     - Snapdragon 765G
   - **CPU**
     - Octa-core Kryo 475
     - 1 x 2.4Ghz + 1 x 2.2 Ghz + 6 x 1.8Ghz
   - **Ram**
     - 6 GB LPDDR4x
   - **Storage**
     - 256gb UFS 2.1
   - **GPU**
     - Qualcomm Adreno 620
   - **Arch**
     - arm64
   - **Screen**
     - 6.7" (170.18mm) 
		1080x2340 (384ppi) 
		Super AMOLED
   - **Cameras**
     - *Front:* 25 MP (wide), No flash
     - *Rear:* 64 MP (wide), LED flash + 8 MP (telephoto), No flash + 16 MP (ultrawide), No flash
   - **SD Card**
     - up to 1tb, Hybrid SIM slot
   - **Network**
     - 5G NR
     - 4G LTE
     - 3G UMTS
     - 2G CDMA
     - 2G GSM
   - **Wifi**
     - 802.11 a/b/g/n/ac
   - **Bluetooth**
     - BT 5.1 with A2DP + aptX
   - **Battery**
     - 4500mah Li-Po, non removeable
   - **Dimensions**
     - 161.6mm (6.36") [h] x 71.1mm (2.8") [w] x 9.2mm (0.36") [d]
   - **Peripherals**
     - A-GPS
     - Accelerometer
     - BeiDou
     - Compass
     - Dual SIM
     - Fingerprint reader
     - FM radio
     - Galileo
     - GLONASS
     - GPS
     - Gyroscope
     - Light sensor
     - NFC
     - Pedometer
     - Proximity sensor
     - Sensor hub
     - USB OTG

***

## Prerequisites

Requirements for the software and other tools to build, test and push 
- [x] Must have ADB and Fastboot installed on PC
- [x] Developer mode enabled on device
- [x] Unlocked Bootloader

***

### Getting Started

1.  Setting Up ADB on Your Phone

    1.  Launch the Settings application on your phone.

    2.  Tap the ``` About Phone ``` option generally near the bottom of the list.

    ![1-About Phone - RESIZED 450wide](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/9529ec78-57c0-4bd0-b515-78f9f941d264)

    3.  Then tap the Build number option seven times to enable Developer Mode. You will see a toast message when it is done.

    ![2-Build Number - RESIZED 450wide](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/b10e3106-3fcb-4147-9e83-69e704481625)

    ![3-3 Steps Away from being a Developer - RESIZED 450wide](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/191535cf-435e-43f2-a6b5-ea44c58eb0c7)

    ![4-1 Step Away from being a Developer - RESIZED 450wide](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/cf24d7a5-76ba-4753-a8a4-302723f60051)

    ![5-You are Now a Developer - RESIZED 450wide](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/f909aee0-0a75-46ef-ba1a-f74fb5e05a56)

    4.  Now go back to ``` Settings > System > Developer Options ``` There will be a menu you can access.

    ![6-Settings - Then System - RESIZED 450wide](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/df9258ce-a186-402b-b5a9-ce97b0876efe)

    ![6 5-Then Advanced - RESIZED 450wide](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/02592ff7-da8a-42a7-aaab-f08583ef0725)

    ![7-Developer Mode - RESIZED 450wide](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/59cfaa7f-d02c-47ae-b5dd-527c8dfa10fa)

    5.  Go in there and enable the USB debugging option.

    ![8-USB Debugging Enabled - RESIZED](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/99e64f71-3e03-478b-8f21-e33130b7f115)

    6.  Also scroll down to 

        ``` Default USB configuration ```

    [IMAGE 9]

   Select

        ``` File Transfer ```

    [IMAGE 10]

    7.  For now, you're done with the process on the phone. Next up, you will need to scroll below and follow the rest of the instructions for setting up your PC.

2.  Setting Up ADB and Fastboot on Your PC

    1.  First you must download ![platform-tools](https://dl.google.com/android/repository/platform-tools-latest-windows.zip) on your pc.

    2.  Unzip the file and save it somewhere on your C:/ drive. My location was:

      ``` C:\platform-tools ```

    3.  Open File Explorer and browse to where you extracted the contents of this ZIP file.

    4.  Right-click an empty area of the File Explorer window and choose Open in Terminal. If you have an older version of Windows without Windows Terminal, you need to hold Shift on the keyboard while right-clicking, then choose Open PowerShell window here.

    5.  Connect your smartphone or tablet to your computer with a USB cable.

    6.  In the PowerShell/Terminal window, enter the following command to launch the ADB daemon.

      ``` ADB devices ```

    7.  On your phone's screen, you should see a prompt to allow or deny USB Debugging access. Tap Allow.

    [IMAGE ALLOW USB DEBUGGING]

    8.  Finally, re-enter the command: ```ADB devices ``` from step 6. If everything was successful, you should now see your device's serial number in the command prompt/Terminal window.

***

#### Installing

3.  Unlocking Bootloader of Device

    1.  Run command:

    ``` adb reboot bootloader ``

    This will get your device into fastboot mode.

    2.  Then run command:

    ``` fastboot devices ```

    If everything was successful, you should now see your device's serial number in the command prompt/Terminal window.

    3.  Next you will need to get your device key. Do this by running command:

    ``` fastboot oem get_unlock_data ```

    4.  It should return a string of characters such as:



    5.  To generate your unlock code, you’ll need to paste together the 5 lines of output into
one continuous string without "bootloader or info" or white spaces. Using the
example above, the line you’d send us would be:



    6.  

A step by step series of examples that tell you how to get a development
environment running

Say what the step will be

    Give the example

And repeat

    until finished

End with an example of getting some data out of the system or using it
for a little demo

***

## Running the tests

Explain how to run the automated tests for this system
