
# LinuxRef

## User Management

**Add User**

    sudo useradd options username
    sudo passwd username  
  
| Options: |  |
|--------------------|----------------------------------|
| -m (--create-home) | -G (--groups)                    |
| -d (--home)        | -s (--shell)                     |
| -u (--uid)         | -c (--comment)                   |
| -g (--gid)         | -e (--expiredate) YYYY-MM-DD     |
| -r (--system)      | -D (--defaults)                  |


Defaults: */etc/default/useradd*

*Example:  
sudo useradd -m -d "/home/newuser" -s "/bin/bash" -c "newaccount" newuser  
sudo passwd*  

<br>
**Remove User**

    sudo userdel *options username*

| Options: |
|----------|
| -r (--remove)   Also remove home and spool |

<br>
**Create Group**

    sudo groupadd options groupname

| Options: |
|----------------|
|-f (--force)    |
|-g (--gid)      |
|-r (--system)   |
|-p (--password) |
|-n (--new-name) |

<br>
**Add User to Group**

    sudo usermod options groupname username

| Options: |
|----------|
| -a (--append) |
| -G (--groups) |

<br>
**Remove User from Group**

    sudo gpasswd options username

| Options: |
|----------|
|--delete  |

<br>
**Delete Group**

    sudo groupdel groupname

<br>
**Change Password**

    sudo passwd options username

Options:
-e (--expire)   force password change
-l  lock
-u  unlock
   
<br>
**Change Username**

    sudo usermod options username

Options:
-l  change location
-d  change home location
-m  move home to new username
    
Example:

> sudo usermod -l user2 -d /home/user2 -m student2

<br>
**Login as User**

    su - username

    sudo -u username command

<br>
**Login as Root**

    su

    su -

    su - root

    sudo *command*

## Disk Management

<br>
**Make Bootable USB**

    sudo dd bs=4M if=iso_location of=device status=progress oflag=sync

<br>
**Mount Device**

    sudo mount device mount_location

<br>
**Determine FS Type**

    findmnt -no FSTYPE location

### btrfs

<br>
**Create Subvolume**

    sudo btrfs subvolume create location
    
    sudo chown -R $(id -u):$(id -g) location

<br>
**List Subvolumes**

    sudo btrfs subvolume list location

<br>
**Delete Subvolume** 

    sudo btrfs subvolume delete location

<br>
**Create Snapshot from Subvolume**

    sudo btrfs subvolume snapshot option subvolume_location snapshot_location

Options:
-r  read-only
  
<br>
**Send Read-Only Snapshot to Drive**

    sudo btrfs send *options snapshot_location* | sudo btrfs receive destination_location

Options:
-p  designate parent subvolume for incremental backups

<br>
**Run in X11**

    GDK_BACKEND=x11
    
### tar

<br>
**tar Command**

    tar [flags] destinationFileName sourceFileName

|Flag | Explanation |
|-----|-------------|
|-c | Create a new archive. |
|-z | Use gzip compression. |
|-j | Use bzip compression. |
|-v | Provide verbose output. |
|-f | Archive file name. |
|-x | Extract from a compressed file. |
|--remove-files | Delete files after archiving. |
|-czvf | Create an archive with gzip in verbose mode to a provided filename. |
|-tvf | View details of a provide archive filename. |
|-xzvf | Extracts a provided gzip archive with provided filename |

*Examples:  
tar -czvf logs_archive.tar.gz \*
tar -tvf logs_archive.tar.gz  
tar -xzvf logs_archive.tar.gz*  

### yt-dlp

<br>
**Download Playlists**

    yt-dlp --ignore-errors --continue --no-overwrites --download-archive progress.txt -o "playlist_url"

### Pacman

[Arch Wiki](https://wiki.archlinux.org/title/Pacman)

<br>
**Install Package**

    pacman -S package_name

<br>
**Remove Package**

    pacman -R package_name

<br>
**Update Packages**

    pacman -Syu

<br>
**Search for Packages**
    
    pacman -Ss package_name
