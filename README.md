# fucking-android

unpack a rootfs of some kind to `/data`

### dealing with no internet

by default android kernels will have a security
module that restricts access to socket() calls to contexes with the subgroup 3003

edit `/etc/group` to include

```bash
inet:x:3003:every user that needs networking
```

otherwise compile your device's kernel without `CONFIG_PARANOID_NETWORK`

### booting with a service manager

edit `/init.rc`

bind mount your rootfs shit to `/`

create the magisk directories and files in your `/data/sbin`

```bash
cd /data/sbin
mkdir .magisk
touch magisk{,32,64,hide.init,policy} resetprop su{,policy}
```

create your directories to be bound in `/`

```bash
mount -o rw,remount /
mkdir /{bin,etc,home.lib,lib64,root,run,usr,var,tmp}
```

modify your android init script

```bash
on post-fs-data
    # gentoo init
    mount none /data suid remount
    mount none /data/bin /bin bind
    mount none /data/etc /etc bind
    mount none /data/home /home bind
    mount none /data/lib /lib bind
    mount none /data/lib64 /lib64 bind
    mount none /data/root /root bind
    mount none /data/run /run bind

    mount none /sbin/.magisk /data/sbin/.magisk bind
    mount none /sbin/.se /data/sbin/.se bind
    mount none /sbin/magisk /data/sbin/magisk bind
    mount none /sbin/magisk32 /data/sbin/magisk32 bind
    mount none /sbin/magisk64 /data/sbin/magisk64 bind
    mount none /sbin/magiskhide /data/sbin/magiskhide bind
    mount none /sbin/magiskinit /data/sbin/magiskinit bind
    mount none /sbin/magiskpolicy /data/sbin/magiskpolicy bind
    mount none /sbin/resetprop /data/sbin/resetprop bind
    mount none /sbin/su /data/sbin/su bind
    mount none /sbin/supolicy /data/sbin/supoilcy bind

    mount none /data/sbin /sbin bind

    mount none /data/sbin/.magisk /sbin/.magisk bind
    mount none /data/sbin/.se /sbin/.se bind
    mount none /data/sbin/magisk /sbin/magisk bind
    mount none /data/sbin/magisk32 /sbin/magisk32 bind
    mount none /data/sbin/magisk64 /sbin/magisk64 bind
    mount none /data/sbin/magiskhide /sbin/magiskhide bind
    mount none /data/sbin/magiskinit /sbin/magiskinit bind
    mount none /data/sbin/magiskpolicy /sbin/magiskpolicy bind
    mount none /data/sbin/resetprop /sbin/resetprop bind
    mount none /data/sbin/su /sbin/su bind
    mount none /data/sbin/supolicy /sbin/supoilcy bind

    mount none /data/tmp /tmp bind
    mount none /data/usr /usr bind
    mount none /data/var /var bind

    # openrc time!!!
    exec - root root -- /bin/su --command /sbin/openrc root default
```
