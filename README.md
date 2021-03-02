# fucking-android

unpack a rootfs of some kind to `/data`

edit `/init.rc`

bind mount your rootfs shit to `/`

```
on post-fs-data
    ...
    
    mount none /data/bin /bin bind
    mount none /data/etc /etc bind
    mount none /data/lib /lib bind
    mount none /data/lib64 /lib64 bind
    mount none /data/root /root bind
    mount none /data/run /run bind
    mount none /data/usr /usr bind
    mount none /data/var /var bind
```

if you have magisk, suffer, it wants to use /sbin
