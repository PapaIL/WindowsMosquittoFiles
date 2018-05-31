# WindowsMosquittoFiles
Installation & Dependency files (dll) for Windows Mosquitto

Mosquitto MQTT Message Service is often needed for Home Automation projects.
 It handles messaging between devices and OpenHAB.

 Installing Mosquitto on Windows can be challenging to have all the right versions of dependent .dll files.
 
 mosquitto-1.4.10-install-win32.exe, the mosquitto installer is not the latest version,
    but it is the latest version I could get to work consistently with the following method.
 
             The following might help you succeed ...
 
   Run the Mosquitto installation .exe file the FIRST time.
 I recommend you use mosquitto-1.4.10-install-win32.exe from this repository.
   You can see several versions at https://ftp.fau.de/eclipse/mosquitto/binary/win32/

Using the installation .exe, install Mosquitto in the default directory, C:\Program Files (x86)\mosquitto
    & also install mosquitto as a service.

Disregard the installer's messages about .dll files to get because they no longer help enough.
    I believe this repository provides the needed .dll files.

 Warning: The first run of mosquitto-****.exe to install Mosquitto may say that it succeeded, 
     but it will not truly be working yet as a service.
 However, the installer's first run will install needed files and folders.

Download all four .dll files from this repository & put them in the C:\Program Files (x86)\mosquitto folder that the installer .exe created.

Now (important), run the mosquitto-****.exe installer program again
    and it should complete successfully, including installing mosquitto as a service.
    
After a successful install, you will likely need to start the mosquitto service running.
   Restarting the computer will accomplish that.
OR you could run cmd.exe as an administrator and there, enter the command   net start mosquitto.

