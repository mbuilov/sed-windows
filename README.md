# sed-windows
Instructions for building [Gnu Sed](https://www.gnu.org/software/sed) as a native windows application

All patches under the same license as sources of [Gnu Sed](https://www.gnu.org/software/sed): [GPLv3](https://www.gnu.org/licenses/gpl-3.0.html) or later

Author of the patches: Michael M. Builov (mbuilov@yandex.ru)

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
- [`sed-4.9-x64.exe`](/../../raw/master/sed-4.9-x64.exe) - sed 4.9 built for Windows10 x64 (sha1sum: 517226430b5a708cc8d2dfa4caa624f6a5b0449a)
- [`sed-4.9-x86.exe`](/../../raw/master/sed-4.9-x86.exe) - sed 4.9 built for Windows10 x86 (sha1sum: ecf1bbc23264ebb19ea71332c5fa0f90e9f23465)
- [`sed-4.9-xp.exe`](/../../raw/master/sed-4.9-xp.exe)   - sed 4.9 built for windowsXP x86 (does not support .UTF-8 locale) (sha1sum: 6b2f68bdb53b59f090e9bfc1c97df219f5622e55)

## Instructions how to create the build patch
- [`sed-4.9-build-patch-howto.txt`](/sed-4.9-build-patch-howto.txt)

## Instructions how to apply build patch to compile sed using native tools only
- [`sed-4.9-build.txt`](/sed-4.9-build.txt)

## Prepared build patches
For x64/Windows10/VS22:
- [`sed-4.9-build-VS22-x64.patch`](/sed-4.9-build-VS22-x64.patch)

For x86/Windows10/VS22
- [`sed-4.9-build-VS22-x86.patch`](/sed-4.9-build-VS22-x86.patch)

For x86/WindowsXP/VS9
- [`sed-4.9-build-VS9-x86.patch`](/sed-4.9-build-VS9-x86.patch)
