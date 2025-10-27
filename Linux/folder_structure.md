# Folder Structure

## System & Boot

* / (root) The top of the filesystem tree. Everything starts here.
* /boot Contains boot loader files (like GRUB) and the Linux kernel (vmlinuz, initrd). Without this, the system won’t boot.
* /dev (devices) Virtual files representing hardware (e.g., /dev/sda for disks, /dev/tty for terminals).

## Core System

* /bin (binaries) Essential user commands needed for single-user mode (e.g., ls, cp, mv, cat).
* /sbin (system binaries) System administration commands (e.g., ifconfig, iptables). Normally used by root.
* /lib (libraries) Shared libraries for binaries in /bin and /sbin.
* /lib64 Same as /lib, but for 64-bit libraries.

## Configuration & Logs

* /etc (etcetera) System-wide configuration files (e.g., /etc/passwd, /etc/fstab).
* /var (variable data) Changing files like logs, spools, caches, databases. Example: /var/log/syslog.

## User Environment

* /home Home directories for normal users (/home/matheus). Stores documents, configs, downloads, etc.
* /root Home directory for the root user.

## Applications

* /usr (user system resources) Big one — contains most installed applications and utilities.
  * /usr/bin → Non-essential user binaries (apps like vim, python3).
  * /usr/sbin → Non-essential system admin binaries.
  * /usr/lib → Libraries for /usr/bin and /usr/sbin.
  * /usr/local → Locally installed software (manual installs, not managed by apt).

## Temporary & Runtime

* /tmp Temporary files. Cleared at reboot.
* /run Runtime data (PID files, sockets). Exists only while system is running.

## Special & Optional

* /mnt (mount) Temporary mount point for external filesystems.
* /media Auto-mounted devices (USBs, external HDDs, DVDs).
* /opt (optional) Optional/add-on software (e.g., commercial apps).
* /srv (service) Data for servers (like web or FTP content).

## Where things belong in this structure

* Kernel & boot stuff → /boot
* Critical commands → /bin, /sbin, /lib
* User applications → /usr/bin, /usr/lib, /opt
* Configuration files → /etc
* Logs & dynamic data → /var
* User data → /home
* Temporary files → /tmp
* External devices → /mnt or /media

## Rule of thumb

* If it’s needed to boot, it goes in /bin, /sbin, /lib, /boot.
* If it’s system configuration, it goes in /etc.
* If it’s user data, it’s under /home.
* If it’s apps/libraries, it’s under /usr.
* If it’s logs or temporary, it’s under /var or /tmp.

```sh
/
├── bin       → Essential user commands (ls, cp, mv, cat...)
├── sbin      → Essential system binaries (fsck, mount, ip...)
├── boot      → Kernel + bootloader files (vmlinuz, initrd, grub)
├── dev       → Device files (sda, tty, null)
├── etc       → System configuration files (/etc/passwd, /etc/fstab)
├── lib       → Shared libraries for /bin and /sbin
│   └── lib64 → 64-bit libraries
├── home      → User home directories (/home/matheus, /home/john)
├── root      → Root user’s home directory
├── tmp       → Temporary files (cleared at reboot)
├── var       → Variable data (logs, cache, mail, spool)
│   └── log   → System logs
├── usr       → User applications & resources
│   ├── bin      → Non-essential user binaries (vim, python3)
│   ├── sbin     → Non-essential system admin commands
│   ├── lib      → Libraries for /usr/bin and /usr/sbin
│   ├── local    → Locally installed software (manual builds)
│   └── share    → Shared, architecture-independent data
├── opt       → Optional/add-on software (third-party apps)
├── srv       → Service data (web server, FTP server files)
├── mnt       → Temporary mount point for filesystems
├── media     → Auto-mounted removable devices (USB, CD-ROM)
└── run       → Runtime data (PID files, sockets, system info)
```
