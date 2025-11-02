WoeUSB: bootable Microsoft Win USB (rufus method, CMD)
====

  git: https://github.com/WoeUSB/WoeUSB/releases/download/v5.2.4/woeusb-5.2.4.bash

    woeusb bash script is FINE (legacy boot works with the older Windows .iso only)  
    - it !DOES DOWNload! (wget) from Rufus the spec img. (Could be hacked if no network environment)  
    - be careful with LONG sync at the end of script  
    - for the qemu checks the X must work (local or ssh)  
    - dependencies:  
        apt: wget wimtools parted ...  
    - dependencies for the qemu checks:  
        apt: ovmf qemu-system-x86  

### Win10_1909_English_x64.iso (Older Microsoft .iso)
    # umount /dev/sdb1
    # umount /dev/sdb2
    # cd
    # bash woeusb-5.2.4.bash --target-filesystem NTFS --device 
        ./W10update/86c16116ebacf9b29e4766dd479b5a79_Win10_1909_English_x64.iso /dev/sdX
      - OK in legacy boot mode
      - OK in UEFI boot mode

    - Check legacy boot: (Win logo... then starts OK)
      qemu-system-x86_64 --enable-kvm -m 2G -drive file=/dev/sdb,format=raw

    - Check UEFI boot:   (display not start...)
      qemu-system-x86_64 --enable-kvm -m 2G -drive file=/dev/sdb,format=raw
        -bios /usr/share/OVMF/OVMF_CODE_4M.fd -drive if=pflash,format=raw,readonly=on,file=/usr/share/OVMF/OVMF_VARS_4M.fd
        -vga std

### Win10_22H2_English_x64.iso (Newer Microsoft .iso)
    # bash woeusb-5.2.4.bash --target-filesystem NTFS --device Win10_22H2_English_x64.iso /dev/sdX
    - crash, when legacy boot mode (changing the MBR 446byte to the older one does not help)
    - OK in UEFI boot mode
 
    - Check legacy boot: (Win logo, then crash)
    - Check UEFI boot:   (display not start...)
    
