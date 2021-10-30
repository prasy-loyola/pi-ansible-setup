# Raspberrypi setup using Ansible

### Automount usb drive on boot
    
https://www.shellhacks.com/raspberry-pi-mount-usb-drive-automatically/


Run the blkid command to find out the UUID of the USB drive:

$ sudo blkid
/dev/mmcblk0p1: LABEL_FATBOOT="boot" LABEL="boot" UUID="6341-C9E5" TYPE="vfat" PARTUUID="ea7d04d6-01"
/dev/mmcblk0p2: LABEL="rootfs" UUID="80571af6-21c9-48a0-9df5-cffb60cf79af" TYPE="ext4" PARTUUID="ea7d04d6-02"
/dev/sda1: UUID="FC05-DF26" TYPE="vfat" PARTUUID="2d72d270-01"
Make a backup and open the /etc/fstab file in your favorite text editor:


`sh
sudo cp /etc/fstab /etc/fstab.back
sudo nano /etc/fstab
`

Line To Add To /etc/fstab
`
UUID=FC05-DF26 /mnt/usb0 ntfs defaults,auto,users,rw,nofail,umask=000 0 0
`


