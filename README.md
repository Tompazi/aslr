# aslr

A simple script to turn [address space randomization](https://en.wikipedia.org/wiki/Address_space_layout_randomization) on, off or inspect its current status on Linux.

## Setup
```
cd /usr/bin/ && sudo wget https://raw.githubusercontent.com/Tompazi/aslr/master/aslr && sudo chmod +x aslr
```

## Usage

```
Usage: aslr [on|off|noheap|0|1|2]
 
Turn address space randomization on, off or inspect its current status.

Without any argument aslr will print the current address space randomization
setting.
 
[off|0]		Turn the process address space randomization off.

[noheap|1]	Make the addresses of mmap base, stack and VDSO page randomized.
		This, among other things, implies that shared libraries will be
		loaded to random addresses.  Also for PIE-linked binaries, the
		location of code start is randomized.

[on|2] 	 	Additionally enable heap randomization. (recommended)
```

### Example:

```
$ aslr
aslr is on
$ aslr off
[sudo] password for root: 
kernel.randomize_va_space = 0
aslr is now off
$ aslr off
aslr is already off

```
