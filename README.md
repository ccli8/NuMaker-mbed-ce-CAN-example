
# Getting started with NuMaker-mbed-can on mbed OS
 
The code works on an mbed OS platform. It reads the messages from CAN and the one of R/G/B LED will turn on or all turn off.
 
Please install [mbed CLI](https://github.com/ARMmbed/mbed-cli#installing-mbed-cli).
 
## Get the example application!

Ontain the mbed-OS library from Windows command prompt

git clone https://github.com/ARMmbed/mbed-os


From the command line of Git Bash, for example:
 
```
hg clone https://developer.mbed.org/teams/Nuvoton/code/NuMaker-mbed-can/
cd NuMaker-mbed-can

```

Make shortcut for mbed-os library within the folder NuMaker-mbed-can
 
### Now compile
 
Invoke `mbed compile` specifying the name of your platform and your favorite toolchain (`GCC_ARM`, `ARM`, `IAR`). For example, for the ARM Compiler 5:
 
```
mbed compile -m NUMAKER_PFM_NUC472 -t ARM
```
 
Your PC may take a few minutes to compile your code. At the end you should get the following result:
 
```
+------------------------+-------+-------+---------+
| Module                 | .text | .data |    .bss |
+------------------------+-------+-------+---------+
| Misc                   | 13163 |    44 | 1051800 |
| drivers                |  1031 |     4 |      28 |
| features/FEATURE_LWIP  |   162 |    16 |      16 |
| hal                    |   542 |     8 |       0 |
| platform               |  1569 |    16 |      92 |
| rtos                   |   144 |     8 |       0 |
| rtos/rtx               |  7418 |   100 |    8396 |
| targets/TARGET_NUVOTON |  8276 |   264 |     104 |
| Subtotals              | 32305 |   460 | 1060436 |
+------------------------+-------+-------+---------+
Allocated Heap: unknown
Allocated Stack: unknown
Total Static RAM memory (data + bss): 1060896 bytes
Total RAM memory (data + bss + heap + stack): 1060896 bytes
Total Flash memory (text + data + misc): 32765 bytes
```
 
### Program your board
 
1. Connect your mbed device to the computer over USB.
1. Copy the binary file to the mbed device .
1. Press the reset button to start the program.
 
Please refer to the documents at the path https://github.com/OpenNuvoton/NuMaker_NuWicam_Samples/
 
## Export the project to Keil MDK and debug your application
 
From the command line, run the following command:
 
```
mbed export -m NUMAKER_PFM_NUC472 -i uvision
```
 
To debug the application:
 
1. Start uVision.
1. Import the uVision project generated earlier.
1. Compile your application and generate an `.axf` file.
1. Make sure uVision is configured to debug over CMSIS-DAP (From the Project menu > Options for Target '...' > Debug tab > Use CMSIS-DAP Debugger).
1. Set breakpoints and start a debug session.
 
![Image of uVision](img/uvision.png)
 
## Troubleshooting
 
1. Make sure `mbed-cli` is working correctly and its version is greater than `0.8.9`
 
 ```
 mbed --version
 ```
 
 If not, you can update it easily:
 
 ```
 pip install mbed-cli --upgrade
 ```
 
2. If using Keil MDK, make sure you have a license installed. [MDK-Lite](http://www.keil.com/arm/mdk.asp) has a 32KB restriction on code size.
 
 