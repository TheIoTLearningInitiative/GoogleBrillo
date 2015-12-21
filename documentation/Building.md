Building
==


#install required packages

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
    $ lunch brilloemulator_x86-eng
    $ make -j4
