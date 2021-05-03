# Windows/x64 - Dynamic NoNull Add RDP Admin (BOKU:SP3C1ALM0V3) Shellcode (387 Bytes)
+ Shellcode Author: Bobby Cooke (boku)
+ Date:             May 2nd, 2021
+ Tested on:        Windows 10 v2004 (x64)
## Shellcode Description:
+ 64bit Windows 10 shellcode that adds user BOKU:SP3C1ALM0V3 to the system and the localgroups Administrators & "Remote Desktop Users". Position Independent Code (PIC) that dynamically resolves KERNEL32 DLL via PEB & LDR. Shellcode contains no null bytes, and therefor can be used on typical stack based Buffer OverFlow vulnerabilities. Shellcode must be executed from a process with either a HIGH or SYSTEM integrity level.

![](x64win-AddRdpAdmin.png)

## Compile & get shellcode from Kali:
```bash
nasm -f win64 addRdpAdmin.asm -o addRdpAdmin.o
for i in $(objdump -D addRdpAdmin.o | grep "^ " | cut -f2); do echo -n "\x$i" ; done
```
