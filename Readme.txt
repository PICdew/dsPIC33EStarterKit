This Readme file provides additional information on using the USB demo with a
dsPIC33E or a PIC24E device. Note that instructions for running the demo are
 provided in the html file contained in the demo folder (the same folder that
contains this Readme file).

This demo does NOT require you to install Microchip Application Libraries (MAL). 
It is self contained. The USB Host/Device Stack file are included in the project
as a archive file (USBStackArchive.a). 

FAQ
---

1. Where is the MPLAB Project/Workspace located?

Ans-> This is located in the Firmware folder contained in the demo folder.

2. What do I do if I have made changes to the USB stack source code or have 
updated the version of MAL on my computer? How do I update USBStackArchive.a?

Ans-> The Firmware folder contains a batch file (BuildUSBArchive.bat). Open the batch
file in Notepad and modify the value of MALPATH variable to match the location
of MAL on your computer. Then run the batch file by double clicking on it. This
will open up a shell window which will display the build process. You can check
this window for any build errors.

Note that the batch file assumes that you have not changed the location where
MPLAB C30 compiler is located. (This is installed by default in 
C:\Program Files\Microchip). You would have to modify the batch file to point to
the correct location if needed.

3. How do I know what USB Stack files are needed by the demo?

Ans-> The Firmware folder in the demo folder contains a file (USBStackFiles.txt)
which lists the .c files and .h files needed by the demo. You can also analyze
the batch file to see what files processes.

4. If the demo is self contained, then why is there a Microchip folder in the
Firmware folder?

Ans-> The Microchip folder contains USB Stack header files needed by the demo.
Some files in the demo (which are not a part of the USB stack) invoke the USB
stack API and hence need the header files. Running the BuildUSBArchive.bat
script will udpate the header files in the local Microchip folder with updated 
files from the MAL folder.

5. I made changes to usb_descriptors.c/usb_config.h/HardwareProfile.h files. Do
I need to run BuildUSBArchive.bat

Ans-> Yes. There may be some dependancy of the USB stack on these files. It is
recommended that the archive be udpated by running the BuildUSBArchive.bat
batch file. 
