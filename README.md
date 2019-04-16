# dashflasher
Bash script to make working with OpenOCD easier for flashing Segway-Ninebot dashboards via stlinkv2

This *may* work with other jtag interfaces besides the stlink-v2 But you'll have to edit the INTF variable yourself to point at the right files.

dashflasher (c)2019 CryptoDragonLady
------------------------------------

Usage: dashflasher [cmd] (dumpfile) (flashfile)

cmd is a number from 0 to 2
0 is read binary data and output to dumpfile (it will append .bin to the dumpfile specified)
1 is write binary data from file flashfile (it will not append .bin to flashfile and expects full path if not in current directory)
2 is read binary data, output to dumpfile, then flash binary data from flashfile

example (to read data and ouput to dumpfile)
dashflasher 0 dashdump

example (to write dump to dashboard)
dashflasher 1 full_BLE.bin

example (to read data and ouput to dumpfile and write to dashboard)
dashflasher 2 dashdump full_BLE.bin

Also, trying to read (dump) using a file that already exists will cause termination of the script, as well as trying to write (flash) a file that doesnt exist

