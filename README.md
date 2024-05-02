Simple Lineage II bot that uses CV to find possible targets and monitor
HP/MP/CP.

Demo videos:
https://www.youtube.com/playlist?list=PLr7PdgzVvrd0OB0Yy9erJKnBfvejsAAaO

Features
========

*   Near and far NPC detection
*   HP/MP/CP monitoring
*   Mouse and keyboard emulation

How to use
==========

NOTE: Interception driver (https://github.com/oblitum/Interception) is required
for mouse and keyboard emulation.

1.  Install Interception driver (https://github.com/oblitum/Interception/releases)
    (start cmd.exe as Administrator, then run install-interception.exe /install)
    and reboot.
2.  Run Lineage II client, select character and teleport to any exp/farm
    location.
3.  Run run.bat "title of the Lineage II client window".
4.  HP/CP/MP bars must be 100% at the moment of bot start, but if not,
    you should wait until it will be 100% and then press Space to reset bars
    position.
5.  To stop press ESC or move mouse.

Default keyboard layout:

*   F1 – Primary attack
*   F2 – Next target
*   F3 – Spoil
*   F4 – Sweep
*   F5 – Pick up
*   F6 – Restore HP when <70%
*   F7 – Restore MP when <70%
*   F8 – Restore CP when <90%

Command-line options
====================

l2cvbot.exe:

    --window    Lineage II window title or part of the title.
                Default: "Lineage II"
    --debug     Show window with debug information. Default: true

run.bat only accepts window title.

Customization
=============

Current version developed and tested using Windows 10 and Gracia Epilogue
client, but with another Windows or Lineage II client it may not work.

*   Edit run.bat to customize CV or keyboard layout for another client. Note
    that for colors are used HSV and BGR color models.
*   Edit Brain.cpp to customize bot behavior and timings. Custom runtime
    behavior scripts currently aren't supported.
*   OS related stuff placed in these files: Window.cpp, Capture.cpp, Input.cpp,
    Intercept.cpp.

Building
========

Use CMake and MSVC (Visual Studio 2017) on Windows.

1.  Download and install CMake (https://cmake.org/download/).
2.  Download OpenCV binaries (https://opencv.org/releases.html) or build OpenCV
    (https://github.com/opencv/opencv) manually (tested with OpenCV 3.4.2).
3.  Set OpenCV_DIR environment variable to path of the OpenCV binaries.
4.  Run build-vs15x64.bat for 64-bit OpenCV or build-vs15x32.bat for 32-bit
    OpenCV (or build.bat to provide custom arch, project generator
    and configuration).
5.  Built executable and dependent dynamic libraries can be found in
    build-<arch>/<configuration> directory (e.g. build-x64/Release).

NOTE: If Interception library building fails, try to install WDK
(https://www.microsoft.com/en-us/download/details.aspx?id=11800).
