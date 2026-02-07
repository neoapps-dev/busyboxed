# `busyboxed`

busyboxed is a tiny script that acts as a busybox applet package manager, it simply clones busybox, edits the config, and builds.

## initial setup

you first got to clone busybox,

```sh
sudo busyboxed setup 1_36_1  # version number, replacing . with _
```

config is mostly empty at first, no applets.. (unless you ran it with the env var $BUSYBOXED_DEFCONFIG="anythinghere").
to add applets,

```sh
sudo busyboxed add busybox awk grep ash [.....]   # note: you dont have to do the same items every time..
```

and to remove applets,

```sh
sudo busyboxed rm [...]
```

and then finally, building the final busybox,

```sh
sudo busyboxed build
```

and busybox will be at `/usr/src/busyboxed/bin/busybox`. feel free to symlink it to /bin/.
