# fucking-android

unpack a rootfs of some kind to `/data`

edit `/init.rc`

bind mount your rootfs shit to `/`

```
on post-fs-data
    # gentoo init
    mount none /data suid remount
    mount none /data/bin /bin bind
    mount none /data/etc /etc bind
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

    mount none /data/usr /usr bind
    mount none /data/var /var bind

    # openrc time!!!
    exec - root root -- /bin/su --command /sbin/openrc root default
```

if you have magisk, suffer, it wants to use /sbin
