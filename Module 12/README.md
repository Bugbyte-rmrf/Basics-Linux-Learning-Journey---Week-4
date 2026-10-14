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

** Types of Processors**

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

### 3. Random Access Memory
The motherboard typically has slots where random-access memory (RAM) can be connected to the system. The 32-bit architecture systems can use up to 4 gigabytes (GB) of RAM, while 64-bit architectures are capable of addressing and using far more RAM.

In some cases, the RAM a system has might not be enough to handle all of the operating system requirements. Once invoked, programs are loaded in RAM along with any data they need to store, while instructions are sent to the processor when they execute.

When the system is running low on RAM, virtualized memory called swap space is used to temporarily store data to disk. Data stored in RAM that has not been used recently is moved over to the section of the hard drive designated as swap, freeing up more RAM for use by currently active programs. If needed, this swapped data can be moved back into RAM at a later time. The system does all of this automatically as long as swap is configured.





### What I Learned

