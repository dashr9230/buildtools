# buildtools
This repository serves as a centralized collection of multiple compiler versions tailored for various matching decompilation projects.

See:
https://github.com/dashr9230/SA-MP
https://github.com/dashr9230/VC-MP

## TODOs
- [ ] A Python script that makes building easier
- [ ] Support for Visual C++ 6.0 Service Pack 3 based workspaces
- [ ] Support for Microsoft Visual Studio .NET 2003 based projects

## Building
### Compiling 'rcon'
1. Download [SA-MP](https://github.com/dashr9230/SA-MP) in ZIP format and extract its content into the `C:\sampcvs037R4\sampcvs\main\` directory.
2. Download [buildtools](https://github.com/dashr9230/buildtools) in ZIP format and extract its content into the `C:\sampcvs037R4\sampcvs\main\` directory.
3. Open Command Prompt and the followings commands in this order:
	1. `set INCLUDE=C:\sampcvs037R4\sampcvs\main\buildtools\vc98\Include`
	2. `set LIB=C:\sampcvs037R4\sampcvs\main\buildtools\vc98\Lib`
	3. `mkdir C:\sampcvs037R4\sampcvs\main\rcon\Release`
	4. `..\buildtools\vc98\Bin\cl.exe @..\buildtools\rcon_cl.tmp`
	5. `..\buildtools\vc98\Bin\link.exe @..\buildtools\rcon_link.tmp`
4. That's it. Your compiled `rcon.exe` binary is in the `C:\sampcvs037R4\sampcvs\main\rcon\Release` directory.
