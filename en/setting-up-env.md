This guide is for Linux Users targetting Ubuntu 18.04 LTS users. This guide does not tend to work with WSL (both V1 and V2), please use real "Linux Environment" or use a "Virtual Machine" or get yourself a server!

**Don't wanna go thru hassles? Introduce [akhilnarang's script](https://github.com/akhilnarang/scripts) repository**
```bash
git clone https://github.com/akhilnarang/scripts; cd scripts; sudo bash setup/android_build_env.sh
```
after you've done these you can skip to [Step 3](#h-3-make-a-folder-and-initialize-repo)

---------------------------------------

### 1: Setting up a build environment! ###

```bash
The Android build is most widely built on Ubuntu LTS (18.04 as of now when this note is made)! These have the pre-built tools to compile the ROM! 
A 64 bit system arch and cpu is a compulsary requirement to build Android Versions from Gingerbread (2.3.x) and higher.
```

### 2: Installing required packages ###
 
```bash
A 64-bit version of Ubuntu (18.04 is recommended as of now because of LTS).

- sudo apt-get install openjdk-8-jdk

- sudo apt-get update && sudo apt-get install git-core gnupg flex bison gperf libsdl1.2-dev libesd0-dev squashfs-tools build-essential zip curl libncurses5-dev zlib1g-dev openjdk-8-jre openjdk-8-jdk pngcrush schedtool libxml2 libxml2-utils xsltproc lzop libc6-dev schedtool g++-multilib lib32z1-dev lib32ncurses5-dev lib32readline-gplv2-dev gcc-multilib maven tmux screen w3m ncftp 
 
(If you face a problem while installing libesd0-dev  package, follow the steps from here: https://askubuntu.com/questions/1082722/unable-to-locate-package-libesd0-dev-on-ubuntu-18-04#)
```

### 3: Make A Folder And Initialize Repo ###

```bash
-  mkdir evo && cd evo

-  repo init -u https://github.com/Evolution-X/manifest -b ten

-  repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

### 4: Building ###

```bash
-  . build/envsetup.sh

-  lunch aosp_$device-userdebug

-  mka bacon
```

That's all you need to do! You're good to compile the build and #KeepEvolving!

**Guide made possible with help by [Reynold Clare](https://t.me/Reynold29)**

**Reference**
* [AOSP](https://source.android.com/setup/build/initializing)


###### All rights reserved 2019-2020, Haruka LLC. (Legal Trademark Holder of Evolution X)
