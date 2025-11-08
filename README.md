# Alpine on Beepy

1. Install alpine on a pi zero 2 w. Use rpi-imager to put alpine on the sd card. At the end when it asks you to overwrite the install disk, do that.
2. `apk add abuild` and `abuild keygen -a`.
3. Clone this repo. cd into the device-sqfmi-beepy directory.
4. `abuild -r` the package and then install it (`apk add ./wherever/it/is.apk`)
5. Reboot! Working beepy on alpine. The kernel modules will rebuild themselves on upgrade thanks to `akms`.


# Use github pages repo

1. Copy the `abuild.rsa.pub` key into `/etc/apk/keys/`.
2. Add `https://adamthiede.github.io/beepy-apkbuilds/beepy-apkbuilds/` to `/etc/apk/repositories`. It's ideal to [tag](https://wiki.alpinelinux.org/wiki/Repositories#Tagged_repository) it so you can pin the package.
3. `apk add device-sqfmi-beepy`
4. Reboot and you'll have a working device!
