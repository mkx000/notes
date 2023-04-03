---
author : 马凯旋
---

### GRUB ( GRUB2 , 支持 BIOS 和 UEFI)

<img src="/home/mkx/github/notes/installOS/pictures/GNU_GRUB_components.svg.png" style="zoom:150%;" />

reference source: https://wiki.debian.org/GRUB2?action=show&redirect=Grub2#Introduction
> [GRUB 2](https://en.wikipedia.org/wiki/GRUB_2) and [elilo](https://en.wikipedia.org/wiki/Elilo) serve as conventional, full-fledged standalone UEFI boot loaders for  Linux. Once loaded by a UEFI firmware, they both can access and boot  kernel images from all devices, partitions and file systems they  support, without being limited to the EFI system partition.
>
> GRUB2 is a bootloader, A bootloader can be thought of as a **mini operating system used to launch an operating system kernel**. GRUB2 can also pass control to another bootloader. This is called "chainloading" and is often needed for dual-boot machines. 
>
> GRUB2 is typically **installed during the installation of Debian itself**. If properly installed, GRUB2 will be **automatically detected by the computer's UEFI during boot (or BIOS for older computers)**. If multiple bootloaders exist on the same computer, such as with a dual boot machine, the user will need to enter their computer's UEFI or BIOS to set the priority order of the bootloaders present since the computer will execute only one bootloader after a successful power-on self-test (POST). They may also need to **turn off the Secure Boot option in UEFI** to stop it from preventing GRUB2 from launching.
>
> GRUB2 **supports multiple operating systems on the same computer** and can  even be configured to present the user a menu of kernels from which to  select.
>
> GRUB supports booting x86 systems via either the traditional BIOS method (aka "Legacy" or "CSM"), or more modern [UEFI](https://wiki.debian.org/UEFI). How they start up is quite different, but in most cases the end result should be all-but-invisible to the user. 

### UEFI (**Unified Extensible Firmware Interface** , 自动探测到 ESP 分区)

A set of [specifications](https://en.wikipedia.org/wiki/Specification_(technical_standard)) written by the [UEFI Forum](https://en.wikipedia.org/wiki/UEFI_Forum).They define the [architecture](https://en.wikipedia.org/wiki/Software_architecture) of the platform [firmware](https://en.wikipedia.org/wiki/Firmware) used for [booting](https://en.wikipedia.org/wiki/Booting) and its [interface](https://en.wikipedia.org/wiki/Interface_(computer_science)) for interaction with the [operating system](https://en.wikipedia.org/wiki/Operating_system). Examples of firmware that implement these specifications are [AMI Aptio](https://en.wikipedia.org/wiki/AMI_Aptio), [Phoenix SecureCore Tiano](https://en.wikipedia.org/wiki/Phoenix_Technologies), [TianoCore EDK II](https://en.wikipedia.org/wiki/TianoCore_EDK_II) and [InsydeH2O](https://en.wikipedia.org/wiki/InsydeH2O).

UEFI replaces the BIOS which was present in the boot ROM of all personal computers that are IBM PC-compatible, although it can provide backwards compatibility with the BIOS using CSM booting.

In addition to the standard PC disk partition scheme that uses a [master boot record](https://en.wikipedia.org/wiki/Master_boot_record) (MBR), UEFI also works with the [GUID Partition Table](https://en.wikipedia.org/wiki/GUID_Partition_Table) (GPT) partitioning scheme, which is free from many of the limitations of MBR. （UEFI 支持MBR和GPT两种分区表）

### EFI system partition (ESP,  引导程序，boot loader，所在的分区)

The **EFI** (**Extensible Firmware Interface**) **system partition**  or **ESP** is a [partition](https://en.wikipedia.org/wiki/Partition_(computing)) on a [data storage device](https://en.wikipedia.org/wiki/Data_storage_device) (usually a [hard disk drive](https://en.wikipedia.org/wiki/Hard_disk_drive) or [solid-state drive](https://en.wikipedia.org/wiki/Solid-state_drive)) that is used by computers having the [Unified Extensible Firmware Interface](https://en.wikipedia.org/wiki/Unified_Extensible_Firmware_Interface) (UEFI). When a computer is [booted](https://en.wikipedia.org/wiki/Booting), UEFI firmware loads files stored on the ESP to start installing [operating systems](https://en.wikipedia.org/wiki/Operating_system) and various utilities.

An ESP contains the [boot loaders](https://en.wikipedia.org/wiki/Boot_loader) or [kernel images](https://en.wikipedia.org/wiki/Kernel_image) for all installed operating systems (which are contained in other partitions), [device driver](https://en.wikipedia.org/wiki/Device_driver) files for hardware devices present in a computer and used by the [firmware](https://en.wikipedia.org/wiki/Firmware) at boot time, system utility programs that are intended to be run before an operating system is booted

The EFI system partition is formatted with a [file system](https://en.wikipedia.org/wiki/File_system) whose specification is based on the [FAT file system](https://en.wikipedia.org/wiki/FAT_file_system) and maintained as **part of the UEFI specification**





## UEFI vs BIOS boot process 

参考这篇文章https://wiki.debian.org/GRUB2?action=show&redirect=Grub2#Introduction

![img](/home/mkx/github/notes/installOS/pictures/UEFI_boot_process.png)

* MBR was sometimes called the first stage Boot Loader.
* MBR partition tables can have a maximum of 4 separate partitions (可以有很多逻辑分区). However, one of those partitions can be configured to be an *extended partition*, which is a partition that can be split up into an 23 additional  partitions. So the absolute maximum number of partitions an MBR  partition table can have is 26 partitions.
* GPT partition tables allow for up to 128 separate partitions, which is more than enough for most real world applications.
* As MBR is older, it's usually paired with older Legacy BIOS systems, while GPT is found on newer UEFI systems. 





## Filesystem Hierarchy Standard（FHS）

[FHS](https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard) is a a reference describing the conventions used for the layout of a UNIX system. In the FHS, all files and [directories](https://en.wikipedia.org/wiki/Directory_(file_systems)) appear under the [root directory](https://en.wikipedia.org/wiki/Root_directory) `/`, **even if they are stored on different physical or virtual devices**.

### /bin 

Essential command [binaries](https://en.wikipedia.org/wiki/Executable) that need to be available in [single-user mode](https://en.wikipedia.org/wiki/Single-user_mode), including to bring up the system or repair it,[[3\]](https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard#cite_note-3) for all users (e.g., [cat](https://en.wikipedia.org/wiki/Cat_(Unix)), [ls](https://en.wikipedia.org/wiki/Ls), [cp](https://en.wikipedia.org/wiki/Cp_(Unix))).


### /boot 

[Boot loader](https://en.wikipedia.org/wiki/Boot_loader) files. In [Linux](https://en.wikipedia.org/wiki/Linux), and other [Unix](https://en.wikipedia.org/wiki/Unix)-like [operating systems](https://en.wikipedia.org/wiki/Operating_system), the /boot/ [directory](https://en.wikipedia.org/wiki/Folder_(computing)) holds files used in [booting](https://en.wikipedia.org/wiki/Booting) the operating system. The usage is standardized in the [Filesystem Hierarchy Standard](https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard)

### /etc
Host-specific system-wide configuration files.

### /lib

[Libraries](https://en.wikipedia.org/wiki/Library_(computer_science)) essential for the [binaries](https://en.wikipedia.org/wiki/Binaries) in `/bin` and `/sbin`.

### /media

Mount points for [removable media](https://en.wikipedia.org/wiki/Removable_media) such as [CD-ROMs](https://en.wikipedia.org/wiki/CD-ROM) (appeared in FHS-2.3 in 2004).

### /mnt

Temporarily [mounted](https://en.wikipedia.org/wiki/Mount_(computing)) filesystems.

### /opt
Add-on application software packages.

### /proc
Virtual filesystem providing process and kernel information as files. In Linux, corresponds to a procfs mount. Generally, automatically generated and populated by the system, on the fly. 

### /run
Run-time variable data: Information about the running system since last boot, e.g., currently logged-in users and running daemons. Files under this directory must be either removed or truncated at the beginning of the boot process, but this is not necessary on systems that provide this directory as a temporary filesystem (tmpfs)

### /sbin
Essential system binaries (e.g., [fsck](https://en.wikipedia.org/wiki/Fsck), [init](https://en.wikipedia.org/wiki/Init), [route](https://en.wikipedia.org/wiki/Route_(command))).

### /srv
Site-specific data served by this system, such as data and scripts for web servers, data offered by FTP servers, and repositories for version control systems 

### /sys

Contains information about devices, drivers, and some kernel features.

