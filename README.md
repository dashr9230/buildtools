# buildtools
This repository serves as a centralized collection of multiple compiler versions tailored for various matching decompilation projects.

See:
- https://github.com/dashr9230/SA-MP
- https://github.com/dashr9230/VC-MP

## TODOs
- [ ] A Python script that makes building easier
- [x] Support for Visual C++ 6.0 Service Pack 6 based workspaces
- [ ] Support for Microsoft Visual Studio .NET 2003 based projects

## Building SA-MP

1. Download [SA-MP](https://github.com/dashr9230/SA-MP) in ZIP format and extract `SA-MP-main` content into the `C:\sampcvs037R4\sampcvs\main\` directory.
2. Download [buildtools](https://github.com/dashr9230/buildtools) in ZIP format and extract `buildtools-main` content into the `C:\sampcvs037R4\sampcvs\main\buildtools` directory.
3. Open **Command Prompt**, choose what you want to compile, and enter their following commands in the given order.

#### Compiling 'rcon'
```batch
cd C:\sampcvs037R4\sampcvs\main\rcon\
set INCLUDE=C:\sampcvs037R4\sampcvs\main\buildtools\msvc60\Include
set LIB=C:\sampcvs037R4\sampcvs\main\buildtools\msvc60\Lib
mkdir C:\sampcvs037R4\sampcvs\main\rcon\Release
..\buildtools\msvc60\Bin\cl.exe @..\buildtools\rcon_cl.tmp
..\buildtools\msvc60\Bin\link.exe @..\buildtools\rcon_link.tmp
explorer.exe C:\sampcvs037R4\sampcvs\main\rcon\Release
```

#### Compiling 'launch3'
```batch
cd C:\sampcvs037R4\sampcvs\main\launch3
set INCLUDE=C:\sampcvs037R4\sampcvs\main\buildtools\msvc60sp6\Include
set INCLUDE=C:\sampcvs037R4\sampcvs\main\buildtools\msvc60sp6\MFC\Include;%INCLUDE%
set LIB=C:\sampcvs037R4\sampcvs\main\buildtools\msvc60sp6\Lib
set LIB=C:\sampcvs037R4\sampcvs\main\buildtools\msvc60sp6\MFC\Lib;%LIB%
mkdir Release
..\buildtools\msvc60sp6\Bin\RC.EXE /l 0x409 /foRelease/launch3.res /d NDEBUG C:\sampcvs037R4\sampcvs\main\launch3\launch3.rc
..\buildtools\msvc60sp6\Bin\cl.exe @..\buildtools\launch3_cl_1.tmp
..\buildtools\msvc60sp6\Bin\cl.exe @..\buildtools\launch3_cl_2.tmp
..\buildtools\msvc60sp6\Bin\link.exe detours.lib /nologo /subsystem:windows /incremental:no /pdb:Release/samp_debug.pdb /machine:I386 /out:Release/samp_debug.exe .\Release\launch3.obj .\Release\launch3Dlg.obj .\Release\StdAfx.obj .\Release\launch3.res
explorer.exe C:\sampcvs037R4\sampcvs\main\launch3\Release
```
