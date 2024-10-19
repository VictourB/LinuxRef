
# LinuxRef

**Run in X11**

> GDK_BACKEND=x11

### yt-dlp

**Download Playlists**

> yt-dlp --ignore-errors --continue --no-overwrites --download-archive progress.txt -o *"playlist_url"*

### Pacman

[Arch Wiki](https://wiki.archlinux.org/title/Pacman)

Install Package
: pacman -S *package_name*

Remove Package
: pacman -R *package_name*

Update Packages
: pacman -Syu

Search for Packages
: pacman -Ss *package_name*

## User Management

**Add User**

> sudo useradd *options username* 
>
> sudo passwd *username*

    Options:
    -m (--create-home)  -G (--groups)
    -d (--home)         -s (--shell)
    -u (--uid)          -c (--comment)
    -g (--gid)          -e (--expiredate) YYYY-MM-DD
    -r (--system)       -D (--defaults)

Defaults: */etc/default/useradd*

Example:

> $ sudo useradd -m -d "/home/newuser" -s "/bin/bash" -c "newaccount" newuser
>
> $ sudo passwd

**Remove User**

> sudo userdel *options username*

    Options:
    -r (--remove)   Also remove home and spool

**Create Group**

> sudo groupadd options *groupname*

    Options:
    -f (--force)
    -g (--gid)
    -r (--system)
    -p (--password)
    -n (--new-name)
    
**Add User to Group**

> sudo usermod *options groupname username*

    Options:
    -a (--append)   -G (--groups)
    
**Remove User from Group**

> sudo gpasswd *options username*

    Options:
    --delete
    
**Delete Group**

> sudo groupdel groupname

**Change Password**

> sudo passwd *options username*

    Options:
    -e (--expire)   force password change
    -l  lock
    -u  unlock
    
**Change Username**

> sudo usermod *options username*

    Options:
    -l  change location
    -d  change home location
    -m  move home to new username
    
Example:

> $ usermod -l user2 -d /home/user2 -m student2

**Login as User**

> $ su - *username*
>
> $ sudo -u *username command*

**Login as Root**

> $ su
>
> $ su -
>
> $ su - root
>
> $ sudo *command*

## Disk Management

**Make Bootable USB**

> sudo dd bs=4M if=*iso_location* of=*device* status=progress oflag=sync

**Mount Device**

> sudo mount *device mount_location*

**Determine FS Type**

> findmnt -no FSTYPE location

### btrfs

**Create Subvolume**

> sudo btrfs subvolume create *location*
>
> sudo chown -R $(id -u):$(id -g) *location*

**List Subvolumes**

> sudo btrfs subvolume list *location*

**Delete Subvolume** 

> sudo btrfs subvolume delete *location*

**Create Snapshot from Subvolume**

> sudo btrfs subvolume snapshot *option subvolume_location snapshot_location*

    Options:
    -r  read-only
    
**Send Read-Only Snapshot to Drive**

> sudo btrfs send *options snapshot_location* | sudo btrfs receive *destination_location*

    Options:
    -p  designate parent subvolume for incremental backups
