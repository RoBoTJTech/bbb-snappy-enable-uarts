#robotjtech-bbb-oem.snap

You can use this pre-built oem snap to build a BeagleBone Black Snappy Core Image that has uarts 0,1,2 and 4 enabled

*To build the image run:*

sudo ubuntu-device-flash core 15.04 -o my-snappy.img --channel edge --oem robotjtech-bbb-oem.snap --enable-ssh --developer-mode

*Then write to your sdcard with:*

sudo dd if=my-snappy.img bs=4k of=DRIVE

Now you can ssh into your BeagleBone Black

The username is "ubuntu" and the password is "ubuntu"


**NOTE:**
substitute the path to the drive e.g. /dev/sdd or /dev/mmcblk0 (not the
path of a partition e.g. /dev/sdd1 or /dev/mmcblk0p1) in place of DRIVE

#If you wish to create your own u-boot.img and MLO
*First install the needed tools:*

sudo apt-get install -y git build-essential make gcc-arm-linux-gnueabihf

*Then download the latest u-boot source tree:* 

git clone git://git.denx.de/u-boot.git

*Then change to the u-boot dir:*

cd u-boot

*Then build the .config file:*

make CROSS_COMPILE=arm-linux-gnueabihf- omap3_beagle_defconfig

*Then compile the the source:*

make CROSS_COMPILE=arm-linux-gnueabihf-

*You now have a new u-boot.img and MLO file. Copy those files to the oem build-source dir and build your oem snap.*



Everything you need to enable additional serial ports on snappy on the BeagleBone Black

For more information on this watch my videos. Part one starts here https://www.youtube.com/watch?v=zPANtXA5634 Part one explains how the dtb files work in Debian Part two explains how you use them in Snappy Core Part three and others will explain how to build custom snappy-core images that include everything you want.

If you need web-hosting or any other technical services check out
#http://www.robotjtech.com
#http://store.robotjtech.com
#http://www.thejohnnyoshow.com
#http://facebook.com/thejohnnyoshow
#http://youtube.com/thejohnnyoshow

Hope you found this useful

John Orjias
  

