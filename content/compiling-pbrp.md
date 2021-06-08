---
title: "Compiling Pbrp"
date: 2021-06-07T12:39:05+05:30
draft: false
---
# Compiling Pitch Black Recovery Project
Compiling PBRP isn't that hard if your device is supported. But if it is not, it is still easy provided that you have a good device tree. In this tutorial, we will use a `on7xelte` a.k.a. `SM-G610F`. 
## YOU NEED TO HAVE LINUX FOR COMPILING. WSL WON'T WORK WELL

## Getting Started
- Acquiring Device Tree
	1. As I have an `on7xelte`, I have **a lot** of device trees and as PBRP is based on TWRP I will choose [this](https://github.com/samsungexynos7870/android_device_samsung_on7xelte/tree/twrp). 
- Getting PBRP sources
	1. Now this part is pretty easy and the time totally depends on your internet speed. It took me about 10mins in 30MiBPS.
	2. Make a Work directory. I will be naming it `pbrp`
	3. To download PBRP sources, `cd` into the work directory and do
```
repo init -u git://github.com/PitchBlackRecoveryProject/manifest_pb.git -b android-10.0
```

And do `repo sync` This will take bit of time to download.

## Compiling PBRP
	1. Do `source build/envsetup.sh` This will work in ZSH and Bash, but I don't know about other's like FISH or SH. This sets up the commands and requirements for building.
	2. Next up, `cd` to `device` and make a directory with the name of your [OEM](https://en.wikipedia.org/wiki/Original_equipment_manufacturer). For me it's gonna be `samsung`. Then `cd` into that and make another directory with your device codename. For me its `on7xelte`. If you don't know your device's codename, just Google it!
	3. Then clone your dev tree in the folder you just made. 
	4. Do `lunch omni_(your device codename)`
	5. Finally to compile, do `mka recoveryimage`. This will compile PBRP. And after its done, go to WORKDIR/out and get the zip!

Have a nice flash!
Otus9051
