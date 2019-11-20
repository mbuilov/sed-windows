# sed-windows
Instructions for building [Gnu Sed](https://www.gnu.org/software/sed) as a native windows application

All patches under the same license as sources of [Gnu Sed](https://www.gnu.org/software/sed): [GPLv3](https://www.gnu.org/licenses/gpl-3.0.html) or later

Author of the patches: Michael M. Builov (mbuilov@gmail.com)

## Fixed bugs:
- wrong directory of input file in in-place editing mode ('-i' switch) (sed: cannot rename ./sed8JEw8l: Improper link)
- new switch '-C' or '--ignore-locale' - forces Sed to use the standard "C" locale instead of the system one; this switch is most usable in binary mode, to avoid possible interpretation of input data as multi-byte encoded strings (depending on the system locale)
- sources were fixed for correct processing of text files with Windows line endings if sed is built under CYGWIN
- now sed is capable for resolving wildcards in file arguments

## Pre-built executables:
- [`sed-4.7.exe`](/sed-4.7.exe)     - sed 4.7 built for windowsXP x86
- [`sed-4.7-x64.exe`](/sed-4.7-x64.exe) - sed 4.7 built for windows7 x64

## Instructions how to create build patch
- [`sed-4.7-build-patch-howto.txt`](/sed-4.7-build-patch-howto.txt)

## Prepared build patches
For x64/Windows7/VS17:
- [`sed-4.7-build-VS17-x64.txt`](/sed-4.7-build-VS17-x64.txt) - instructions how to apply the patch to compile sed using native tools only
- [`sed-4.7-build-VS17-x64.patch`](/sed-4.7-build-VS17-x64.patch)

For x86/WindowsXP/VS9
- [`sed-4.7-build-VS9-x86.txt`](/sed-4.7-build-VS9-x86.txt) - instructions how to apply the patch to compile sed using native tools only
- [`sed-4.7-build-VS9-x86.patch`](/sed-4.7-build-VS9-x86.patch)
