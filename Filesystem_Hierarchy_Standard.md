# LinuxRef

## Filesystem Hierarchy Standard (FHS) 


| Location      | Details       |
| ------------- | ------------- |
| /             | Primary hierarchy root and root directory of the entire file system hierarchy.|
| /bin          |Essential command binaries that need to be available in single-user mode, including to bring up the system or repair it, for all users (e.g., cat, ls, cp). |
| /boot | Boot loader files (e.g., kernels, initrd). |
| /dev | Device files (e.g., /dev/null, /dev/disk0, /dev/sda1, /dev/tty, /dev/random). |
| /etc | Host-specific system-wide configuration files. |
| /etc/opt | Configuration files for add-on packages stored in /opt. |
| /etc/sgml | Configuration files, such as catalogs, for software that processes SGML. |
| /etc/X11 | Configuration files for the X Window System, version 11. |
| /etc/xml | Configuration files, such as catalogs, for software that processes XML. |
| /home | Users' home directories, containing saved files, personal settings, etc. |
| /lib | Libraries essential for the binaries in /bin and /sbin. |
| /lib\<qual> | Alternate format essential libraries. These are typically used on systems that support more than one executable code format, such as systems supporting 32-bit and 64-bit versions of an instruction set. Such directories are optional, but if they exist, they have some requirements. |
| /media | Mount points for removable media such as CD-ROMs (appeared in FHS-2.3 in 2004). |
| /mnt | Temporarily mounted filesystems. |
| /opt | Add-on application software packages. |
| /proc | Virtual filesystem providing process and kernel information as files. In Linux, corresponds to a procfs mount. Generally, automatically generated and populated by the system, on the fly. |
| /root | Home directory for the root user. |
| /run | Run-time variable data: Information about the running system since last boot, e.g., currently logged-in users and running daemons. Files under this directory must be either removed or truncated at the beginning of the boot process, but this is not necessary on systems that provide this directory as a temporary filesystem (tmpfs). | 
| /sbin | Essential system binaries (e.g., fsck, init, route). |
| /srv | Site-specific data served by this system, such as data and scripts for web servers, data offered by FTP servers, and repositories for version control systems (appeared in FHS-2.3 in 2004). | Contains information about devices, drivers, and some kernel features. |
| /sys | Contains information about devices, drivers, and some kernel features. |
| /tmp | Directory for temporary files (see also /var/tmp). Often not preserved between system reboots and may be severely size-restricted. |
| /usr | Secondary hierarchy for read-only user data; contains the majority of (multi-)user utilities and applications. Should be shareable and read-only. |
| /usr/bin | Non-essential command binaries (not needed in single-user mode); for all users. |
| /usr/include | Standard include files. |
| /usr/lib | Libraries for the binaries in /usr/bin and /usr/sbin. |
| /usr/libexec | Binaries run by other programs that are not intended to be executed directly by users or shell scripts (optional). |
| /usr/lib\<qual> | Alternative-format libraries (e.g., /usr/lib32 for 32-bit libraries on a 64-bit machine (optional)). |
| /usr/local | Tertiary hierarchy for local data, specific to this host. Typically has further subdirectories (e.g., bin, lib, share). |
| /usr/sbin | Non-essential system binaries (e.g., daemons for various network services). |
| /usr/share | Architecture-independent (shared) data. |
| /usr/src | Source code (e.g., the kernel source code with its header files). |
| /usr/X11R6 | X Window System, Version 11, Release 6 (up to FHS-2.3, optional). |
| /var | Variable files: files whose content is expected to continually change during normal operation of the system, such as logs, spool files, and temporary e-mail files. |
| /var/cache | Application cache data. Such data are locally generated as a result of time-consuming I/O or calculation. The application must be able to regenerate or restore the data. The cached files can be deleted without loss of data. |
| /var/lib | State information. Persistent data modified by programs as they run (e.g., databases, packaging system metadata, etc.). |
| /var/lock | Lock files. Files keeping track of resources currently in use. |
| /var/log | Log files. Various logs. |
| /var/mail | Mailbox files. In some distributions, these files may be located in the deprecated /var/spool/mail. |
| /var/opt | Variable data from add-on packages that are stored in /opt. |
| /var/run | Run-time variable data. This directory contains system information data describing the system since it was booted. In FHS 3.0, /var/run is replaced by /run; a system should either continue to provide a /var/run directory or provide a symbolic link from /var/run to /run for backwards compatibility. |
| /var/spool | Spool for tasks waiting to be processed (e.g., print queues and outgoing mail queue). |
| /var/spool/mail | Deprecated location for users' mailboxes. |
| /var/tmp | Temporary files to be preserved between reboots. |

## Other Locations

-   /var/lib/pacman
-   /etc/passwd
-   /etc/shadow
-   /etc/group
-   /etc/skel
-   ~/.bash_profile
-   ~/.bashrc
