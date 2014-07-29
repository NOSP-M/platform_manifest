[Team Nocturnal Open Source Project](team-nocturnal.com)
====================================


Download the source
--------------

Please read the [NOSP building instructions](http://forums.team-nocturnal.com/index.php/topic/1876-) before proceeding.

Initialize:

Create the build directory :

    $ mkdir ~/dev
    $ mkdir ~/dev/nosp
    $ cd ~/dev/nosp
Init core trees without any device/kernel/vendor :

    $ repo init -u https://github.com/NOSP/platform_manifest.git -b nosp444

Init repo with all devices, kernels and vendors supported by NOSP :

    $ repo init -u https://github.com/NOSP/platform_manifest.git -b nosp444 -g all,kernel,device,vendor

Init repo only for a particular device

    $ repo init -u https://github.com/NOSP/platform_manifest.git -b nosp444 -g all,-notdefault,<devicename>,<vendorname>

for example, to init only trees needed to build Hammerhead

    $ repo init -u https://github.com/NOSP/platform_manifest.git -b nosp4442 -g all,-notdefault,hammerhead,lge

sync repo

    $ repo sync

***

Building
--------

After the sync is finished, please read the [instructions from the Android site](http://s.android.com/source/building.html) on how to build.

    . build/envsetup.sh
    brunch


You can also build (and see how long it took) for specific devices like this:

    . build/envsetup.sh
    time brunch nosp_hammerhead-userdebug

Remember to `make clobber` every now and then!

