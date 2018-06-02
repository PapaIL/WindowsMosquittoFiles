# WindowsMosquittoFiles
Installation & Dependency files (dll) for Windows Mosquitto

Mosquitto MQTT Message Service is often needed for Home Automation projects.
 It handles messaging between devices and OpenHAB.

 Installing Mosquitto on Windows can be challenging, matching a good install .exe 
     with the right versions of dependent .dll files where needed.

  What seems to work:  running a relatively high mosquitto .exe installer
(I chose mosquitto-1.4.15-install-win32.exe from https://ftp.fau.de/eclipse/mosquitto/binary/win32/ )
   AND putting high versions of these in the mosquitto program folder:
      libeay32.dll  pthreadVC2.dll  ssleay32.dll  vcruntime140.dll

         I provide all 5 of the above files in this repository.

     The following worked for me and might help you succeed ...
 
   Download this repositories files to where you can find them.
 
Using the installation .exe, install Mosquitto in the default directory, C:\Program Files (x86)\mosquitto
    AND also install mosquitto as a service.

Disregard the installer's messages about .dll files to get because
      some are wrong versions and one source is overkill.
         I believe this repository provides the needed files.

 Warning: When finished, the mosquitto-****.exe to install Mosquitto may say that it succeeded, 
     but it will not truly be working yet as a service.
 However, running the installer will install needed files and folders.

Next move all four .dll files from this repository into the C:\Program Files (x86)\mosquitto folder that the installer .exe created.

      Mosquitto should now have all it needs.  One more thing to do ...
    
After a successful install, you likely need to start the mosquitto service running.
   A) Restarting the computer will accomplish that.
OR B) run cmd.exe as an administrator and there, enter:  net start mosquitto.
    Or C) run services.msc, scroll down,
        right mouse click on Mosquitto Broker, and use a left mouse click to choose start.

              Congratulations.   Mosquitto service should now be running.
A) and C) above will show you that it started running

               PS I'm creating a script to automate much of the above.
