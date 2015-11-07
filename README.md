## Pull source
```shell
$ repo init -u https://github.com/nctusenselab/manifest -b default
$ repo sync -jX
```

## Building environment using docker
```
$ git clone https://github.com/nctusenselab/aosp_buildenv_dockerfile
$ cd aosp_buildenv_dockerfile/
$ docker build -t="android-x86-kitkat-test1" . # -t="<IMAGE_NAME>"
$ docker run -ti -v=`pwd`:/root/android/ android-x86-kitkat-test1 bash
```

## Build android x86 with SVMP support
```
$ . build/envsetup.sh
$ lunch android_x86-eng
$ m -jX iso_img
```

## Run
```
$ qemu-system-x86_64 --enable-kvm -hda sense.qcow2 -cdrom sense.iso -boot d -serial stdio -m 4G -smp 4 -net nic,vlan=0 -net user,hostfwd=tcp:127.0.0.1:8001-:8001,hostfwd=tcp:127.0.0.1:5555-:5555 -soundhw all -vga cirrus
```
