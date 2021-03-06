# WindowsMosquittoFiles
Installation & Dependency files (dll) for Windows Mosquitto

Mosquitto MQTT Message Service is often needed for Home Automation projects.
 It handles messaging between devices and OpenHAB.

 Installing Mosquitto on Windows can be challenging, matching a good install .exe 
     with the right versions of dependent .dll files where needed.

Note: As of Jan. 21, 2019, I am running Windows 10 Home, Version 10.0.17763 Build 17763.

   What seems to work:  running a relatively high mosquitto .exe installer
     AND putting high versions of these in the mosquitto program folder:  	msvcr120.dll
       libcrypto-1_1.dll  libeay32.dll  libssl-1_1.dll  pthreadVC2.dll  ssleay32.dll  vcruntime140.dll

(I chose mosquitto-1.4.15a-install-win32.exe from https://ftp.fau.de/eclipse/mosquitto/binary/win32/ 
     Version 1.14.15a gave no virus alerts.  Caution: version 1.14.15 did give a virus / trojan alert. I was not able to make these files work: mosquitto-1.5.1-install-windows-x86.exe or xxx.2 or xxx.3 ie xxx.4 )

         I provide all 8 of the above files in this repository.

     The following worked for me and might help you succeed ...
 
   Download this repository's files to where you can find them, maybe C:\~PapaFiles
 
Using Mosquitto-****.exe, install Mosquitto in the default directory, C:\Program Files (x86)\mosquitto
    AND also install mosquitto as a service.

Disregard the installer's messages about .dll files to get because
      some are wrong versions and one source is overkill.
         I believe this repository provides the needed files.

 Warning: When finished, the mosquitto-****.exe installer may say that it succeeded, 
     but it will not truly be working yet as a service.
 However, running the installer will install needed files and folders.

Next copy all six .dll files from this repository into the C:\Program Files (x86)\mosquitto folder that the mosquitto-****.exe created.

   Next, using Mosquitto-****.exe a SECOND time, 
install Mosquitto in the default directory, C:\Program Files (x86)\mosquitto
    AND also install mosquitto as a service.

      Mosquitto should now have all it needs. Let's get it running & working.
    
After a successful install, you likely need to start the mosquitto service running.
   A) Restarting the computer will accomplish that.
OR B) run cmd.exe as an administrator and there, enter:  net start mosquitto.
    Or C) run services.msc, scroll down,
        right mouse click on Mosquitto Broker, and use a left mouse click to choose start.
        
A) and C) will show you that the mosquitto service started running.

      One more thing, test that Mosquitto is truly working ...

In the search box of Windows Start Button or Cortana, enter cmd twice ...
   to open 2 command line windows on the screen. Arrange them side by side.
   
In one cmd window enter: "C:\Program Files (x86)\mosquitto\mosquitto_sub" -h 127.0.0.1 -t house/#
    (subscribes to any message published in the topic "house")
       In window 2, to publish a message in the topic "house" enter:
"C:\Program Files (x86)\mosquitto\mosquitto_pub" -h 127.0.0.1 -m "Mosquitto MQTT Message Service is working" -t house/test -d

     If the message displays in window 1, Mosquitto service should now be running.  Congratulations.

PS In my https://github.com/PapaIL/WindowsScriptsForOH repository, I put one script to automate much of the above & another script to test that mosquitto is working.
         
   Note: vcruntime140.dll came from https://www.dll4free.com/pthreadvc2.dll.html.
The other .dll files came from http://slproweb.com/download/Win32OpenSSL_Light-1_0_2o.exe
   and https://slproweb.com/download/Win32OpenSSL_Light-1_1_0h.exe
   
If the above Mosquitto install does not work, you may not have the Microsoft-Visual-C-Redistributables that you need. In the https://github.com/PapaIL/Microsoft-Visual-C-Redistributables repository, I provided 3 install files that worked for me. Download & run the files starting with the 2010 file.  If your Windows computer says it already has a Microsoft-Visual-C-Redistributables install, cancel the install & go on to another install file. After you install the missing Microsoft-Visual-C-Redistributables, try the above Windows Mosquitto install again.
