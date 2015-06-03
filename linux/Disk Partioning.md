Dependencies:

* GNU Parted
* Linux mke2fs

First label and partion a drive:

```
parted _drive directory_
>mklabel _label type_
>mkpart _partition-type filesystem start end_
```

Example:

```
parted /dev/sda`
>mklabel gpt`
>mkpart primary ext2 0% 100%`
```
Format the drive:

`[mke2fs config] _drive directory_`

Example:

`mkfs.ext4 /dev/sda`
