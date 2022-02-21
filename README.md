**Android ROM for JingPad A1**
==============================

This ROM is based on the official Android ROM for JingPad A1, whose source code was [released](https://forum.jingos.com/t/android-rom-source-code-for-jingpad-a1/2738) by JingLing on their official forum.

**Table of contents**
---------------------

* [Prerequisites](#prerequisites)
* [Package bring-up](#package-bring-up)
* [Compiling](#compiling)

**Prerequisites**
-----------------

In order to build the Android ROM .pac file, you need at least:
* 250 GB (or more) of free storage
* 16 GB of RAM

If you just have 16 GB of RAM, **don't run Ubuntu VM on Windows**, otherwise it will crash.

**Package bring-up**
--------------------

You must use Ubuntu 18.04 LTS.

First of all, install these dependencies using apt and aptitude:

```
sudo apt-get update

sudo apt-get install fakeroot dpkg-dev libcurl4-openssl-dev python python3 repo python-pip python3-pip

sudo apt-get install aptitude -y

sudo aptitude install bc bison build-essential ccache curl flex g++-multilib gcc-multilib gnupg gperf imagemagick lib32ncurses5-dev lib32readline-dev lib32z1-dev liblz4-tool libncurses5-dev libsdl1.2-dev libssl-dev libwxgtk3.0-dev libxml2 libxml2-utils lzop pngcrush rsync schedtool squashfs-tools xsltproc zip zlib1g-dev

sudo aptitude install -y openjdk-8-jdk
```

Then, install this python module:

```
sudo pip install pycryptodome
sudo pip3 install pycryptodome
```
and
```
sudo pip install pycrypto
sudo pip3 install pycrypto
```

**Compiling**
-------------
### Scenario 1 (recommended)
If you want to completely compile without the out directory and then package the .pac file, run these commands:

```
cd vendor/sprd/release/IDH/Script/

./build_pac.sh -a ud710_3h10u_native-userdebug-native -b build 2>&1 | tee build.log

./build_pac.sh -a ud710_3h10u_native-userdebug-native -b pac 2>&1 | tee build.log
```
### Scenario 2
If you want to completely compile and package .pac file without out directory just running only one command, just do:
```
cd vendor/sprd/release/IDH/Script/

./build_pac.sh -a ud710_3h10u_native-userdebug-native -b all 2>&1 | tee build.log
```
