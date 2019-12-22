# sed-windows
Instructions for building [Gnu Sed](https://www.gnu.org/software/sed) as a native windows application

All patches under the same license as sources of [Gnu Sed](https://www.gnu.org/software/sed): [GPLv3](https://www.gnu.org/licenses/gpl-3.0.html) or later

Author of the patches: Michael M. Builov (mbuilov@gmail.com)

## Fixed bugs:
- wrong directory of input file in in-place editing mode ('-i' switch) (sed: cannot rename ./sed8JEw8l: Improper link)
- sources were fixed for correct processing of text files with Windows line endings (if Sed is built under CYGWIN)
- fixed support of UTF-8 locale (e.g. "Russian_Russia.UTF-8", available starting with Windows 7)
- fixed interaction with standard Windows console in UTF-8 code page (set by chcp 65001)

## Added features:
- native Sed is capable for resolving wildcards in file arguments
- native Sed takes locale settings from environment variables LC_ALL, LC_CTYPE or LANG
- new switch '-C' or '--ignore-locale' - forces Sed to use the standard "C" locale; this switch is most usable in binary mode, to avoid possible interpretation of input data as multi-byte encoded strings (depending on the system locale)
- new switch '--locale' - to explicitly specify locale to use (and ignore environment variables LC_ALL, LC_CTYPE and LANG)

## Pre-built executables:
- [`sed-4.7-x64.exe`](/sed-4.7-x64.exe) - sed 4.7 built for windows7 x64
- [`sed-4.7-xp.exe`](/sed-4.7-xp.exe)   - sed 4.7 built for windowsXP x86 (does not support .UTF-8 locale)

## Instructions how to create the build patch
- [`sed-4.7-build-patch-howto.txt`](/sed-4.7-build-patch-howto.txt)

## Prepared build patches
For x64/Windows7/VS19:
- [`sed-4.7-build-VS19-x64.patch`](/sed-4.7-build-VS19-x64.patch) - patch for building Sed as a native Windows application
- [`sed-4.7-build-VS19-x64.txt`](/sed-4.7-build-VS19-x64.txt) - instructions how to apply the patch to compile Sed using native tools only

For x86/WindowsXP/VS9
- [`sed-4.7-build-VS9-x86.patch`](/sed-4.7-build-VS9-x86.patch) - patch for building Sed as a native Windows application
- [`sed-4.7-build-VS9-x86.txt`](/sed-4.7-build-VS9-x86.txt) - instructions how to apply the patch to compile Sed using native tools only
