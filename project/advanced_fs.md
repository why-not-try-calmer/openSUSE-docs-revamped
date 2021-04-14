## Enable zstd compression
First enable `zstd` compression on `/` (root) and `/home` by adding the corresponding parameters to `/etc/fstab`:

```
<UUID> / btrfs compress=zstd:1 0 0
<UUID> /home btrfs subvol=/@/home,compress=zstd:1 0 0
```

This will apply `zstd` compression to all the files directly under the relevant directories. The files already present under these directories will not be touched, however. To retroactively compress them, use:

`sudo btrfs filesystem defrag -czstd -rv / /home/`

