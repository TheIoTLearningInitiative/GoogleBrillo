Building
==


    $ mkdir brillo
    $ cd brillo
    $ repo init -q -u https://android.googlesource.com/brillo/manifest
    $ repo sync -q
    $ cd brillo
    $ source build/envsetup.sh
    $ lunch brilloemulator_x86-eng
    $ make -j4
