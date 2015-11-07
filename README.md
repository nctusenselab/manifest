## Pull source
```shell
$ repo init -u https://github.com/nctusenselab/manifest -b default
$ repo sync -jX
```

## Build environment using docker
```
$ git clone https://github.com/nctusenselab/aosp_buildenv_dockerfile
$ cd aosp_buildenv_dockerfile/
$ docker build -t="android-x86-kitkat-test1" . # -t="<IMAGE_NAME>"
$ docker run -ti -v=`pwd`:/root/android/ android-x86-kitkat-test1 bash
```

## build android x86 with SVMP support
```
$ . build/envsetup.sh
$ lunch android_x86-eng
$ m -jX iso_img
```
