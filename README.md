# LVM backup made easy

This wrapper script creates temporary snapshot of a logical volume, sends it to
Proxmox Backup Server and finally destroys the snapshot.
The content of lv might be stored as raw image [1] or as filessytem archive [2].
In 2nd case the snapshot is automatically mounted before backup and unmounted after.

This script should be run as root (or via sudo, or possibly via sudo -E).

# USAGE:

    [1]   lvm2pbs archivename.img  my_vg/lv_name
    [2]   lvm2pbs archivename.pxar my_vg/lv_name [fstype]

See configuration variables inside the script.

# EXAMPLE:

    lvm2pbs my-rootfs.pxar pve1/root ext4
