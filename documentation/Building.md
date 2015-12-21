Building
==

    $ cd
    $ apt-get update
    $ apt-get install openjdk-7-jdk
    $ apt-get -y -qq install git-core gnupg flex bison gperf build-essential \
      zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 \
      lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z-dev ccache \
      libgl1-mesa-dev libxml2-utils xsltproc unzip
    $ mkdir ~/bin
    $ PATH=$PATH:~/bin
    $ curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
    $ chmod a+x ~/bin/repo
    $ mkdir brillo
    $ cd brillo
    $ repo init -q -u https://android.googlesource.com/brillo/manifest
    $ repo sync -q
    $ cd brillo
    $ source build/envsetup.sh
    $ lunch
    
    You're building on Linux

    Lunch menu... pick a combo:
    1. aosp_arm-eng
    2. aosp_arm64-eng
    3. aosp_mips-eng
    4. aosp_mips64-eng
    5. aosp_x86-eng
    6. aosp_x86_64-eng
    7. brilloemulator_arm64-eng
    8. brilloemulator_arm-eng
    9. brilloemulator_x86_64-eng
    10. brilloemulator_x86-eng
    11. edison-eng
    12. mini_emulator_arm64-userdebug
    13. m_e_arm-userdebug
    14. mini_emulator_x86_64-userdebug
    15. mini_emulator_x86-userdebug
    16. brillo_gpios-userdebug
    17. brillo_i2c-userdebug
    18. brillo_leds-userdebug
    19. ledflasher-userdebug
    
    Which would you like? [aosp_arm-eng] 9

    ============================================
    PLATFORM_VERSION_CODENAME=REL
    PLATFORM_VERSION=6.0
    TARGET_PRODUCT=brilloemulator_x86_64
    TARGET_BUILD_VARIANT=eng
    TARGET_BUILD_TYPE=release
    TARGET_BUILD_APPS=
    TARGET_ARCH=x86_64
    TARGET_ARCH_VARIANT=x86_64
    TARGET_CPU_VARIANT=
    TARGET_2ND_ARCH=x86
    TARGET_2ND_ARCH_VARIANT=x86
    TARGET_2ND_CPU_VARIANT=
    HOST_ARCH=x86_64
    HOST_OS=linux
    HOST_OS_EXTRA=Linux-3.16.0-43-generic-x86_64-with-Ubuntu-14.04-trusty
    HOST_CROSS_OS=windows
    HOST_BUILD_TYPE=release
    BUILD_ID=MASTER
    OUT_DIR=out
    ============================================
    
    $ make -j4
    $ export ANDROID_BUILD_TOP=/path/to/brillo/
    $ ./out/host/linux-x86/bin/brilloemulator-x86
    export PS1=’$(whoami)@$(hostname):$(pwd)> 
    $ ./out/host/linux-x86/bin/brilloemulator-x86
    

