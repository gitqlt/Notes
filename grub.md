GRUB practical
====

**Regenerate GRUB boot in dual-boot EFI environment**

    # fdisk -l /dev/sda
        /dev/sda1       2048     206847    204800   100M EFI System
        /dev/sda7  702326784  849127423 146800640    70G Linux filesystem
    # ls /mnt/p1
        EFI 'System Volume Information'
    # grub-install -v -d /mnt/p7/usr/lib/grub/x86_64_efi --boot-directory=/mnt/p7/boot --efi-directory=/mnt/p1
**Regenerate device.map (optional)**

    # grub-mkdevicemap -m /mnt/sda7/boot/grub/device.map
    
    
