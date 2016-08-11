#robotjtech-bbb-oem.snap

You can use this pre-built oem snap to build a Beagle Boone Black Snappy Core Image that has uarts 0,1,2 and 4 enabled

To build the image run:
sudo ubuntu-device-flash core 15.04 -o my-snappy.img --channel edge --oem robotjtech-bbb-oem.snap --enable-ssh --developer-mode

Then burn to your sdcard with:
sudo dd if=my-snappy.img bs=4k of=<drive>
sync

**NOTE:**
# substitute the path to the drive e.g. /dev/sdd or /dev/mmcblk0 (not the
# path of a partition e.g. /dev/sdd1 or /dev/mmcblk0p1) in place of <drive>



