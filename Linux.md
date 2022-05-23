# Linux
#computer-science 

Linux is a open-source [[operating system]] [[kernel]]. The main purpose of the kernel is to present and abstraction layer to processes running on the operating system; the Linux kernel abstracts away all hardware from the process. Instead, interaction with the hardware is done by processes via [[system calls|system calls]], which the kernel in turn translates to the hardware it's running on.

The linux kernel is comprised of five main subsystems that communicate using procedure calls.

## System Architecture

- [[User Applications]]
- [[OS Services]]
- Linux Kernel
- [[Hardware Controllers]]

## Kernel Structure
- [[Process Scheduler]]
- [[Memory Manager]]
- [[Virtual File System]]
- [[Network Interface]]
- [[Inter-Process Communication]]

![[Pasted image 20220522230754.png]]

Far and away the most important subsystem piece here is the process scheduler.

## File System

Linux file systems implement a [[virtual file system]] that the kernel talks to. The VFS translates [[system calls]] from the [[kernel]] to whatever underlying filesystem type is being used.