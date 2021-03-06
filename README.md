# Lineage buildscripts
========================

Please note, I use ~/android/lineage in this README but you can use whatever folder name you want.

First I recommend checking the official LineageOS wiki instructions for building for Z01R here to see what are the dependencies and how to install them
https://wiki.lineageos.org/devices/Z01R/build

Also please note that repopick.sh isn't always updated. Please check LineageOS Gerrit in case there is changes to repopick topics.

Starting from zero:
---------
    mkdir -p ~/android/lineage-19.1
    cd ~/android/lineage-19.1
    repo init -u git://github.com/LineageOS/android.git -b lineage-19.1
    mkdir -p .repo/local_manifests
    curl https://raw.githubusercontent.com/5z-devs/local_manifests/lineage-19.1/asus.xml > .repo/local_manifests/asus.xml
    repo sync

If you've already synced Lineage-Sources:
----------
    mkdir -p .repo/local_manifests
    curl https://raw.githubusercontent.com/5z-devs/local_manifests/lineage-19.1/asus.xml > .repo/local_manifests/asus.xml
    repo sync

Building
----------
    cd ~/android/lineage
    curl https://raw.githubusercontent.com/5z-devs/local_manifests/lineage-19.1/Z01R_clean_build.sh > Z01R_clean_build.sh
    curl https://raw.githubusercontent.com/5z-devs/local_manifests/lineage-19.1/Z01R_dirty_build.sh > Z01R_dirty_build.sh
    ./Z01R_clean_build.sh // for Z01R clean builds
    ./Z01R_dirty_build.sh // for Z01R dirty builds

I made these modified build scripts for convenience plus logs terminal output to files for easy scrolling later in your favorite text editor.

Please note! In my modified build scripts I disabled ccache as I use mine at /mnt/ccache whereas you might not, so you must set it up for yourself.