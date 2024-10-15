# BBR2Decompile
Heavily WIP Decompilation of Blasterball Revolution 2.

# So Far
In progress works of decompiling BBR2, we have discovered that it is an C/C++ compiled executable.
Which are known to be near impossible. If it werent for the fact the dissaembly can actually be done, because its an **PEI-i386**, an Portal Executable mainly for an x86 assembly.
Which is easy to dissamble, but not decompile.

However the code is intact which, it can be used to convert to an ELF format with an immense long struggle converting instructions; Or it can be reconstructed as an windows executable.

# DLL Discovery/Registery

Researching the imports of said executable for windows reveals that half of the dll's are used for Network Configuration.
> 0 : MSVCR71.DLL : Library Required for PHP

> 1 : WINMM.DLL : Windows Multimedia API

> 2 : DDRAW.DLL : DirectDraw[DirectX API]

> 3 : USER32.DLL : Windows API for Native windows controls

> 4 : ole32.DLL : Component Object Model Linking and Embedding

> 5 : ADVAPI32.DLL : Windows 32bit Security caller/Windows Register

> 6 : MSACM32.DLL : 32x Audio Compression Module

> 7 : KERNEL32.DLL : Base Application Manipulation with System

> 8 : GDI32.DLL : Graphics Device Interface Renderer

> 9 : SHELL32.DLL : Opening Web pages/files Library

> 10 : OLEAUT32.DLL : Generic Microsoft OLE Automation Library

> 11 : WS2_32.DLL : Service Provider Interface Loader DLL

> 12 : WININET.DLL : Network Acessing info Library

> 13 : IPHLPAPI.dll : Library for retrieving network configuration info.

Using the Installer Executable from archive.org (Or at least before it was hacked as of October 15, 24')
Actually reveals that the network is not necessary, especially when the high score uploading system, does not even remotely work. (Inside of wine, that it didn't throw an error even in debug.)

The rest are basic necessaries for applications on windows.
#0 Can be ignored if its only looking for php
#1 Can be replaced with something like libargus
#2 Can be replaced with OpenGL
#3 Can be replaced with default Linux Windows Controls api
#4 Unk
#5 Can be ignored or replaced
#6 Can be replaced with default system audio or an equivilant 32bit audio compressed like WavPack
#7 Will be replaced with Linux Default
#8 Can be replaced with OpenGL
#9 Can be Ignored as web pages cannot open
#10 Unk
#11 Linux Default
#12 Can be ignored as an app shouldn't be acessing network if it doesn't work.
#13 Can be ignored as an app shouldn't be retrieving network config if it doesn't work.

# To DO
Obviously we need to start further disassemble the code or translate into an language that can be read before swapping out and in: imports and structs.

I have tried converting it to an Linux(0) 32bit binary, with objdump and stripping headers however I am figuring out segmentation faults without an proper IDE on that end.
While still trying to research into base windows executable to see what makes it tick and decompile it into an language that would make **Readable**.


