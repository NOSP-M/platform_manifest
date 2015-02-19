[Team Nocturnal Open Source Project](http://team-nocturnal.com)
====================================


Download the source
--------------

Please read the [NOSP building instructions](http://forums.team-nocturnal.com/index.php/forum/62-) before proceeding.

Initialize:

Create the build directory :

    $ mkdir ~/dev
    $ mkdir ~/dev/nosp
    $ cd ~/dev/nosp
Init core trees without any device/kernel/vendor :

    $ repo init -u https://github.com/NOSP/platform_manifest.git -b nosp500

sync repo

    $ repo sync

***

Building
--------

After the sync is finished, please read the [instructions from the Android site](http://s.android.com/source/building.html) on how to build.

    . build/envsetup.sh
    brunch
    make -j4


You can also build (and see how long it took) for specific devices like this:

    . build/envsetup.sh
    time brunch nosp_hammerhead-user
    make -j4

Remember to `make clobber` every now and then!

