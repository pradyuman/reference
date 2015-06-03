Dependencies:

* GNU Parted
* Linux mke2fs

First label and partion a drive:

```
parted [drive directory]
>mklabel [label type]
>mkpart [partition type] [filesystem type] [start] [end]
```
Example:

```
parted /dev/sda
> mklabel gpt
> mkpart primary ext2 0% 100%
```
Format the drive:

`[mke2fs config] [drive directory]`

Example:

`mkfs.ext4 /dev/sda`
