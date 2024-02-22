# Lineage buildscripts
========================

First I recommend checking the official LineageOS wiki instructions for building for Z01R here to see what are the dependencies and how to install them
https://wiki.lineageos.org/devices/Z01R/build

Also please note that repopick.sh isn't always updated. Please check LineageOS Gerrit in case there is changes to repopick topics.

Starting from zero:
---------
    # cd into your ROM's folder (IE, from scratch I would mkdir -p ~/android/lineage-21 && cd ~/android/lineage-21)
    repo init -u https://github.com/LineageOS/android.git -b lineage-21.0 --git-lfs
    mkdir -p .repo/local_manifests
    curl https://raw.githubusercontent.com/5z-devs/local_manifests/lineage-21/asus.xml > .repo/local_manifests/asus.xml
    repo sync

If you've already synced Lineage-Sources:
----------
    # cd into your ROM's folder
    mkdir -p .repo/local_manifests
    curl https://raw.githubusercontent.com/5z-devs/local_manifests/lineage-21/asus.xml > .repo/local_manifests/asus.xml
    repo sync

Building
----------
    # cd into your ROM's folder
    curl https://raw.githubusercontent.com/5z-devs/local_manifests/lineage-21/Z01R_clean_build.sh > Z01R_clean_build.sh
    curl https://raw.githubusercontent.com/5z-devs/local_manifests/lineage-21/Z01R_dirty_build.sh > Z01R_dirty_build.sh
    ./Z01R_clean_build.sh // for Z01R clean builds
    ./Z01R_dirty_build.sh // for Z01R dirty builds

I made these modified build scripts for convenience plus logs terminal output to files for easy scrolling later in your favorite text editor.

Please note! In my modified build scripts I disabled ccache as I use mine at /mnt/ccache whereas you might not, so you must set it up for yourself.
