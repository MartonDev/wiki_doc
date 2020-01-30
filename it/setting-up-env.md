Questa guida è rivolta agli utenti Linux che usano Ubuntu 18.04 LTS. Questa guida non tende a funzionare con WSL (sia V1 che V2), utilizza il vero "ambiente Linux" o usa una "macchina virtuale" o procurati un server!

**Non vuoi passare attraverso le seccature? Guarda gli [script di akhilnarang](https://github.com/akhilnarang/scripts)**
```bash
git clone https://github.com/akhilnarang/scripts; cd scripts; sudo bash setup/android_build_env.sh
```
dopo che hai fatto questo passa al [Punto 3](#h-3-crea-una-cartella-e-inizializza-la-repo)

---------------------------------------

### 1: Creare un ambiente per il building! ###

```bash
Il building di Android avviene maggiormente su sistemi Ubuntu LTS (18.04 a partire da quando viene fatta questa nota)! Questi hanno gli strumenti predefiniti per compilare la ROM!
Un sistema e una CPU a 64 bit sono obbligatori per creare versioni di Android da Gingerbread (2.3.x) e successive.
```

### 2: Installare i packages richiesti ###
 
```bash
Una versione a 64bit di Ubuntu (18.04 è consigliato perchè è LTS).

- sudo apt-get install openjdk-8-jdk

- sudo apt-get update && sudo apt-get install git-core gnupg flex bison gperf libsdl1.2-dev libesd0-dev squashfs-tools build-essential zip curl libncurses5-dev zlib1g-dev openjdk-8-jre openjdk-8-jdk pngcrush schedtool libxml2 libxml2-utils xsltproc lzop libc6-dev schedtool g++-multilib lib32z1-dev lib32ncurses5-dev lib32readline-gplv2-dev gcc-multilib maven tmux screen w3m ncftp 
 
(Se hai problemi mentre installi libesd0-dev, segui queste indicazioni: https://askubuntu.com/questions/1082722/unable-to-locate-package-libesd0-dev-on-ubuntu-18-04#)
```

### 3: Crea una cartella e inizializza la Repo ###

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

Questo è tutto ciò che devi fare! Buona fortuna e #KeepEvolving!

**Guida creata con l'aiuto di [Reynold Clare](https://t.me/Reynold29)**

**Riferimenti**
* [AOSP](https://source.android.com/setup/build/initializing)


###### All rights reserved 2019-2020, Haruka LLC. (Legal Trademark Holder of Evolution X)
