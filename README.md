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

    [IMAGE 1]

    3.  Then tap the Build number option seven times to enable Developer Mode. You will see a toast message when it is done.

    [IMAGE 2]
    [IMAGE 3]
    [IMAGE 4]
    [IMAGE 5]

    4.  Now go back to ``` Settings > System > Developer Options ``` There will be a menu you can access.

    [IMAGE 6]
    [IMAGE 6.5]
    [IMAGE 7]

    5.  Go in there and enable the USB debugging option.

    [IMAGE 8]

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
