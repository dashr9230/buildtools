# buildtools
This repository serves as a centralized collection of multiple compiler versions tailored for various matching decompilation projects.

See:
- https://github.com/dashr9230/SA-MP
- https://github.com/dashr9230/VC-MP

## TODOs
- [ ] A Python script that makes building easier
- [ ] Support for Visual C++ 6.0 Service Pack 6 based workspaces
- [ ] Support for Microsoft Visual Studio .NET 2003 based projects

## Building
### Compiling 'rcon'
1. Download [SA-MP](https://github.com/dashr9230/SA-MP) in ZIP format and extract its content into the `C:\sampcvs037R4\sampcvs\main\` directory.
2. Download [buildtools](https://github.com/dashr9230/buildtools) in ZIP format and extract its content into the `C:\sampcvs037R4\sampcvs\main\` directory.
3. Open Command Prompt and enter the following commands in this order:
```batch
cd C:\sampcvs037R4\sampcvs\main\rcon\
set INCLUDE=C:\sampcvs037R4\sampcvs\main\buildtools\msvc60\Include
set LIB=C:\sampcvs037R4\sampcvs\main\buildtools\msvc60\Lib
mkdir C:\sampcvs037R4\sampcvs\main\rcon\Release
..\buildtools\msvc60\Bin\cl.exe @..\buildtools\rcon_cl.tmp
..\buildtools\msvc60\Bin\link.exe @..\buildtools\rcon_link.tmp
```
5. That's it. Your compiled `rcon.exe` binary is in the `C:\sampcvs037R4\sampcvs\main\rcon\Release` directory.
