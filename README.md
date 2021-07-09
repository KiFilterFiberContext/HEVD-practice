# HEVD-practice
> short personal writeups for Hacksys Extreme Vulnerable Driver (HEVD)

## Setup
It is recommended that prior to fuzzing any driver to setup a VM for kernel debugging and analysis.  I will be using a Windows 7 VM setup in VMWare for development and will perform kernel debugging using WinDBG.  It is suggested to follow the guide appropriate for your workstation.

__WinDBG__

The commands are the same on both Windows 7 and Windows 10 to setup kernel debugging.
I will be debugging over a serial connection although it is recommended to debug over the network.

- Enabling Debug Mode: `bcdedit.exe /set debug on` 
- Serial Connection: `bcdedit /dbgsettings serial debugport:2 baudrate:115200`   

![image](https://user-images.githubusercontent.com/51222153/123498466-e8cde700-d5e4-11eb-8f45-6159ed3c3f7c.png)


## Windows 7 vs Windows 10
There are several exploit mitigations that have been introduced since Windows 7 including:
- PTE base randomization
- kCFG
- HVCI/VBS
- NULL page mapping prevention 
- KVA Shadowing (KPTI)
- SMEP / SMAP
- HAL heap base randomization
- NX kernel pools
- Low IL filtering

with more to come featured in Windows 10 Insider Builds such as CET and XFG.
