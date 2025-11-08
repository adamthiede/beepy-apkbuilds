# Alpine on Beepy

1. Install alpine on a pi zero 2 w. Use rpi-imager to put alpine on the sd card. At the end when it asks you to overwrite the install disk, do that.
2. Copy the `abuild.rsa.pub` key in this repo into `/etc/apk/keys/`.
3. Add `https://adamthiede.github.io/beepy-apkbuilds/beepy-apkbuilds/` to `/etc/apk/repositories`. It's ideal to [tag](https://wiki.alpinelinux.org/wiki/Repositories#Tagged_repository) it so you can pin the package.
4. `doas apk add device-sqfmi-beepy`

# Build it yourself

1. `apk add abuild`, `abuild keygen -a`, `doas adduser $USER abuild`
2. Clone this repo. cd into the device-sqfmi-beepy directory.
3. `abuild -r` to build the package. then install it (`apk add ~/packages/beepy-apkbuilds/device-sqfmi-beepy*.apk`)
4. Reboot! The kernel modules will rebuild themselves on every kernel upgrade thanks to `akms`.

