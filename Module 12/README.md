## Introduction

The module covered basic understanding computer hardware, motherboards, processors, Random Access Memory, buses, hard drives, solid state disks, optical drives, managing devices, video display devices and power supplies.

The screenshots included in this README provide evidence of the commands I used and the results I obtained while completing the exercise.

---

### 1. Understanding Computer Hardware
 I learned that computers begin as a hardware device but can grow to encompass virtual machines that are entirely constructed out of software and appear to all purposes to be a remote machine that users can access via remote protocols and methods.

There are hundreds of specific types of computers in service, from set-top boxes to dedicated firewalls to laptops, servers and many special-purpose devices, but they all feature at least a few of the same basic components that actually make them a computer. 

---

### 2. Motherboards

**Motherboard**, or **system board** - It is the main hardware board in the computer through which the central processing unit (CPU), random-access memory (RAM) and other components are all connected. 

Depending on the computer type (laptop, desktop, server) some devices, such as processors and RAM, are attached directly to the motherboard, while other devices, such as add-on cards, are connected via a bus.

---

### 3. Processors

**Central Processing Unit (CPU or processor)** - It is the brain of the computer, where the execution of code takes place and where most calculations are done.

**Multiprocessor** - A hardware system that has more than one processor.

**Multi-core** - If more than one processor is combined into a single overall processor chip.

I learned that `arch` command allows you to see which family the CPU of the current system belongs to:

<img width="616" height="43" alt="Screenshot from 2026-10-14 19-28-16" src="https://github.com/user-attachments/assets/309cc014-91e4-41e0-9fd4-7cb5b1d18705" />

**Types of Processors**

- *x86 system* - the system processes data 32 bits at a time; on an x86_64 the system processes data 64 bits at a time.
- *x86_64 system* -is also capable of processing data 32 bits at a time in a backward compatible mode.

I also learned that `lscpu` command gives more information concerning the CPU:

<img width="609" height="114" alt="Screenshot from 2026-10-14 19-29-30" src="https://github.com/user-attachments/assets/46ec75b2-6d85-4eae-b7aa-666355e06fd7" />

The first line of this output shows that the CPU is being used in a *64-bit mode*, as the architecture reported is *x86_64*. The second line of output shows that the CPU is capable of operating in either a *32-* or *64-bit mode*, therefore, it is actually a *64-bit* CPU.

---

### What I Learned

I learned that the processor is directly connected (soldered) to the motherboard, as motherboards are typically configured to work with specific types of processors.

I also learned that one of the main advantages of a 64-bit system is the ability to work with more memory, while other advantages include increased efficiency of processing and increased security.

---

### 4. Random Access Memory
I learned that the 32-bit architecture systems can use up to 4 gigabytes (GB) of RAM, while 64-bit architectures are capable of addressing and using far more RAM.

When the system is running low on RAM, virtualized memory called **swap space** is used to temporarily store data to disk. 

Data stored in RAM that has not been used recently is moved over to the section of the hard drive designated as swap, freeing up more RAM for use by currently active programs. 

If needed, this swapped data can be moved back into RAM at a later time. The system does all of this automatically as long as swap is configured.

I learned that `free` command to view the amount of RAM in the system, including the swap space. The following options apply with `free` command:

- `-m` option - force the output to be rounded to the nearest megabyte (MB)
- `-g` option to force the output to be rounded to the nearest gigabyte (GB)

<img width="609" height="149" alt="Screenshot from 2026-10-14 19-45-30" src="https://github.com/user-attachments/assets/99a9836d-05e2-41c7-949d-a00e46fe69c0" />

### What I Learned
 I learned that the motherboard typically has slots where random-access memory (RAM) can be connected to the system. 

In some cases, the RAM a system has might not be enough to handle all of the operating system requirements. Once invoked, programs are loaded in RAM along with any data they need to store, while instructions are sent to the processor when they execute.

---

### 5. Buses

**Bus** - It is a high-speed connection that allows communication between computers or the components inside a computer. 

The motherboard has buses that allow for multiple devices to connect to the system, including:
- Peripheral Component Interconnect (PCI) and
- Universal Serial Bus (USB).

---

**a) Peripheral Devices**

**Peripheral devices** - Components connected to a computer that allow input, output or data storage. 

Run `lspci` command to view all of the devices connected by the PCI bus.

The following is a sample output of this command. 

<img width="798" height="95" alt="Screenshot from 2026-10-14 20-01-08" src="https://github.com/user-attachments/assets/02cce54e-a48c-447c-b331-20969257a099" />

The highlighted sections show this system has a VGA controller (a monitor connector), an SCSI storage controller (a type of hard drive) and an Ethernet controller (a network connector)

---

**b) Universal Serial Bus Devices**

I learned that USB devices are *hot-plug*, meaning they can be connected or disconnected while the system is running.

Devices connected internally are usually *cold-plug*, meaning the system must be shut down in order to connect or disconnect a device. 

Though USB devices are hot-plug by design, it's important to ensure that any mounted filesystems are correctly unmounted, or data loss and corruption of the filesystem may occur.

I also learned that `lsusb` command display the devices connected to the system via USB.

<img width="798" height="95" alt="Screenshot from 2026-10-14 20-01-08" src="https://github.com/user-attachments/assets/ecff57b1-ed8e-4368-971d-a2a079d20b13" />

---

### What I Learned

 I learned that in a desktop or server computer, there is a motherboard with the processor, RAM, and other components directly attached, and then a high-speed bus that allows additional components to be attached via card slots, such as video, network and other peripheral devices. 

I also learned that for laptop and light/thin/small form factor computers, the majority of the computer’s components may be directly connected to the motherboard, including the usual processor, RAM, as well as additional components like the network card. In this configuration, the bus still exists, but effectively one of the main convenience factors of being able to swap out or upgrade devices is no longer a possibility.

I also learned that keyboards, mice, monitors, printers and hard disks are all considered peripherals and are accessed by the system in order to perform functions outside of central processing. 

---

### 6. Hard Drives

**Hard drives / hard disks / disk devices or storage devices** - Any electromechanical or electronic storage device that holds data to be accessed by the system.

**Partition** -  A logical division of a hard drive, designed to take a large amount of available storage space and break it up into smaller areas. 

**Master Boot Record (MBR)** - A partitioning technology used by some hard drives.  It has been used since the early days of the Personal Computer (PC). The old term (fixed disk) gave rise to several command names: the `fdisk`, `cfdisk` and `sfdisk` commands, which are tools for working with the MBR partitioned disks.

**GUID Partitioning Table (GPT)** - A partitioning type used by hard drives.It has been available since the year 2000.  GPT allows having partitions which can be larger than two terabytes (MBR does not). The tools for managing GPT disks are named similarly to their `fdisk` counterparts: `gdisk`, `cgdisk`, and `sgdisk`.

**Both GUID & GPT types** - A family of tools that attempt to support both MBR and GPT type disks such as `parted` command and graphical `gparted` tool.

---

### File Names / Device Files Associated with Hard Drives

The device files are stored in the /dev directory. Each device file name is made up of multiple parts.

**a) File Type**

The file name is prefixed based on the different types of hard drives. *IDE (Intelligent Drive Electronics)* hard drives begin with `hd`, while *USB, SATA (Serial Advanced Technology Attachment)* and *SCSI (Small Computer System Interface)* hard drives begin with `sd`.

**b)Device Order**

Each hard drive is then assigned a letter which follows the prefix. For example, the first IDE hard drive would be named `/dev/hda` and the second would be `/dev/hdb`, and so on.

**c)Partition**

Finally, each partition on a disk is given a unique numeric indicator. For example, if a USB hard drive has two partitions, they could be associated with the `/dev/sda1` and `/dev/sda2` device files.

<img width="578" height="34" alt="Screenshot from 2026-10-14 20-47-59" src="https://github.com/user-attachments/assets/298c3ff4-1fcb-44bf-90de-3a4f2a579d2d" />

The `fdisk` command can be used to display further information about the partitions:

<img width="614" height="216" alt="Screenshot from 2026-10-14 20-48-34" src="https://github.com/user-attachments/assets/e199380a-68a8-4329-b711-bb805a40b5eb" />

---

### What I Learned

*Microsoft Windows* to have a single partition for each hard drive, on *Linux distributions*, multiple partitions per hard drive is common.

The GPT disks use a newer type of partitioning, which allows the user to divide the disk into more partitions than what MBR supports.

---

### 7. Solid State Disks

**Solid state disks** -  A larger capacity USB thumb drives in construction and function. 

As there are no moving parts and spinning disks, just memory locations to be read by the controller, a solid state disk is measurably and visibly faster in accessing the information stored in its memory chips.

A solid state disk is controlled by an embedded or onboard processor that makes the decisions as to where and how data is written and read back from the memory chips when requested.

---

**Advantages of a solid state disk**

- Lower power usage,
- Time savings in system booting,
- Faster program loads, and
- Less heat and vibration from no moving parts.

---

**Disadvantages of a solid state disk**

- Higher costs in comparison to spinning hard disks,
- Lower capacity due to the higher cost, and if soldered directly on the motherboard/mainboard, no ability to upgrade by swapping out the drive.

---

### 8. Optical Drives

Optical drives, often referred to as CD-ROMs, DVDs, or Blu-Ray, are removable storage media. While some devices used with optical disks are read-only, others are capable of burning (writing to) disks, when using a writable type of disk. There are various standards for writable and rewritable disks, such as CD-R, CD+R, DVD+RW, and DVD-RW.

Where these removable disks are mounted in the file system is an important consideration for a Linux administrator. Modern distributions often mount the disks under the /media folder, while older distributions typically mount them under the /mnt folder. For example, a USB thumb drive might be mounted on the /media/usbthumb path.

Upon mounting, most GUI interfaces prompt the user to take some action, such as open the contents of the disk in a file browser or start a media program. When the user is finished using the disk, it is necessary to unmount it using a menu or the umount command.



### What I Learned
Consider the difference between a traditional spinning platter hard disk and a USB thumb drive. The former literally has spinning disk platters in it that are read by drive heads, and the spinning disks are laid out to take advantage of the spinning nature of the device. Data is written (and read) in long strings of sequential blocks that a drive head encounters as the platter spins around.

---

### 9. Managing Devices

