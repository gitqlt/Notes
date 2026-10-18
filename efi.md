EFI,UEFI: Modern firmware interface built into motherboard to initializes hardware and controls booting
====
#### Show boot entries
    # efibootmgr [-v]
    (remember: lsblk -o name,UUID,PARTUUID /dev/sda)

#### Create boot entry at the top
    # efibootmgr -c -d /dev/sda -p 9 -L ManualEFI -l '\EFI\mylinux\shimx64.efi'

#### Delete entry
    # efibootmgr -b 3 -B
    
#### Define boot order
    # efibootmgr -o 0001,0002,0000

#### Device EFI partition ( p9, usually mounted at /boot/efi; vfat,FAT32 )
    ├── EFI
        ├── SeagateST500
        └── ubuntu
            └── grub.cfg
            └── grubx64.efi
            └── mmx64.efi
            └── shimx64.efi
        └── BOOT
            └── BOOTX64.EFI
            └── fbx64.efi
            └── mmx64.efi
