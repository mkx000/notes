---
author : 马凯旋
---

### 分区工具

**GParted** ：  GParted is used for creating, deleting,[[3\]](https://en.wikipedia.org/wiki/GParted#cite_note-3) resizing,[[4\]](https://en.wikipedia.org/wiki/GParted#cite_note-4) moving, checking, and copying [disk partitions](https://en.wikipedia.org/wiki/Partition_(computing)) and their [file systems](https://en.wikipedia.org/wiki/File_systems). This is useful for creating space for new [operating systems](https://en.wikipedia.org/wiki/Operating_systems), reorganizing disk usage, copying data residing on hard disks, and  mirroring one partition with another (disk imaging). It can also be used to format a USB drive.

> The disk stores the information about the partitions' locations and  sizes in an area known as the **partition table** that the operating system  reads before any other part of the disk.   **Each partition then appears to the operating system as a distinct "logical" disk that uses part of the actual disk**
>
> Partitioning allows the use of different filesystems to be installed for different kinds of files.   Separating user data from system data can prevent the system partition from becoming full and rendering the system unusable. Partitioning can also make backing up easier.
>
> On [Unix](https://en.wikipedia.org/wiki/Unix)-based and [Unix-like](https://en.wikipedia.org/wiki/Unix-like) operating systems such as [Linux](https://en.wikipedia.org/wiki/Linux), [macOS](https://en.wikipedia.org/wiki/MacOS), [BSD](https://en.wikipedia.org/wiki/BSD), and [Solaris](https://en.wikipedia.org/wiki/Solaris_(operating_system)), it is possible to use multiple partitions on a disk device. Each partition can be formatted with a [file system](https://en.wikipedia.org/wiki/File_system) or as a [swap partition](https://en.wikipedia.org/wiki/Swap_partition).



### 分区

Multiple partitions allow directories such as [/boot](https://en.wikipedia.org/wiki//boot), [/tmp](https://en.wikipedia.org/wiki//tmp), [/usr](https://en.wikipedia.org/wiki//usr), [/var](https://en.wikipedia.org/wiki//var), or [/home](https://en.wikipedia.org/wiki//home) to be allocated their own filesystems. Such a scheme has a number of advantages:

- If one file system gets corrupted, the data outside that filesystem/partition may stay intact, minimizing data loss.
- Specific [file systems](https://en.wikipedia.org/wiki/File_system) can be mounted with different parameters, e.g., [read-only](https://en.wikipedia.org/wiki/File_system_permissions), or with the execution of [setuid](https://en.wikipedia.org/wiki/Setuid) files disabled.
- A runaway program that uses up all available space on a non-system filesystem does not fill up critical filesystems.
- Keeping user data such as documents separate from system files  allows the system to be updated with lessened risk of disturbing the  data.

#### Linux 最简分区
A common minimal configuration for Linux systems is to use **three partitions**: one holding the system files mounted on "/" (the root directory), one holding user configuration files and data mounted on /home (home directory), and a swap partition. 

#### multi-boot systems
Multi-boot systems are computers where the user can boot into more than one distinct operating system (OS) stored in separate storage devices or in separate partitions of the same storage device. In such systems a menu at startup gives a choice of which OS to boot/start (and only one OS at a time is loaded).

This is distinct from virtual operating systems, in which one operating system is run as a self-contained virtual "program" within another already-running operating system. (An example is a Windows OS "virtual machine" running from within a Linux OS.) 

### GUID Partition Table （GPT table）
The GUID Partition Table (Globally Unique IDentifier) is a **part of the Unified Extensible Firmware Interface (UEFI) standard for the layout of the partition table on a physical hard disk**. Many operating systems now support this standard. However, Windows doesn't support this on BIOS based computers.

### Partition table
A **partition table** is a table maintained on a disk by the operating system that outlines and describes the partitions on that disk.The term is most commonly associated with the MBR partition table of a Master Boot Record (MBR) in PCs, but it may be used generically to refer to other formats that divide a disk drive into partitions, such as: **GUID Partition Table (GPT)**, Apple partition map (APM),[12] or BSD disklabel.

As of the mid-2010s, **most new computers use the GUID Partition Table (GPT) partitioning scheme instead**.