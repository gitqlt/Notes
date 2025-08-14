Samba: access to SMB/CIFS resources on servers
====

### List shares:
    $ smbclient -U [MYGROUP/]myuser -L //smbserver
    $ smbclient -U myuser -W mygroup -L //smbserver

### Connect to share:
    $ smbclient -U [MYGROUP/]myuser //smbserver/share
    smb: \> cd myDir

### Mount share/myDir:
    # mount.cifs //smbserver/share/myDir /mnt/mountDir -o 'user=MYUSER,uid=UID,gid=GID,file_mode=0664,dir_mode=0775'
