# SerialS.py

Small Python program to spy on serial communication. Requires the null-modem emulator
com0com to be set up (http://com0com.sourceforge.net/). Have whatever program you want
to spy on talk to a virtual port you've set up using that utility. Configure
`computerPort` in the main file to be the complimentary port. `devicePort` should be
the port of your physical device.

Turns this:

     _____________________________________________          __________ 
    |                   COMPUTER                  |        |  DEVICE  |
    |                                             |        |          |
    |                                             |        |          |
    | Program------------------------------COMx---|--------|          |
    |                                             |        |          |
    |_____________________________________________|        |__________|


Into this (using com0com):

     _______________________________________________        __________ 
    |                   COMPUTER                    |      |  DEVICE  |
    |                        _____________________  |      |          |
    |                       |     serialSpy.py    | |      |          |
    | Program--virtualCOMy--|--virtualCOMz--COMx--|-|------|          |
    |                       |_____________________| |      |          |
    |_______________________________________________|      |__________|
