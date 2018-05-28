# WindowsMosquittoFiles
Installation & Dependency files (dll) for Windows Mosquitto

Mosquitto MQTT Message Service is often needed for Home Automation projects.
 It handles messaging between devices and OpenHAB.

 Installing Mosquitto on Windows can be challenging to have all the right versions of dependent .dll files.
             The following should help you succeed ...
 
   Run the Mosquitto installation .exe file the FIRST time.
 You can use mosquitto-1.4.15a-install-win32.exe from this repository OR
   download the latest Mosquitto binary installation for Windows Vista up
           from mosquitto.org/download/.

Using the installation .exe, install Mosquitto in the default directory, C:\Program Files (x86)\mosquitto
    & also install mosquitto as a service.

Disregard the installer's messages about .dll files to get because they no longer help enough.
    This repository provides the needed .dll files.

 Warning: The first run of mosquitto-****.exe to install Mosquitto will likely FAIL, 
     but it will have installed needed files and folders.

Download all the .dll files from this repository & put them in the C:\Program Files (x86)\mosquitto folder.

Now (important), run the mosquitto-****.exe install program again
    and it should complete successfully.
