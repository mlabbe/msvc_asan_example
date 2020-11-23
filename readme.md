# Address Sanitizer on Windows #

Tested on Visual Studio 2019.

This is an example sln showing how to use address sanitizer on Windows.

Note in order to launch using msvc debugger, Debug > Windows > Exception Settings and uncheck 0xc0000005 checkbox.

## Compiling ##

It should compile as-is, but if you get a linker error:

The project settings links a full path `C:\Program Files (x86)\Microsoft Visual studio\2019\Community\VC\Tools\Llvm\x64\lib\clang\10.0.0\lib\windows\clang_rt.asan-x86_64.lib`.  This may change based on your msvc install.  Find the location of your `clang_rt.asan-x86_64.lib` file and replace it.

## Changes from a default sln ##

 - Platform toolset changed to clang/llvm
 - `-faddress=sanitizer` to additional compiler settings
 - compile with `/MT` 
 - link `clang_rt.asan-x86_64.lib`
 - Do NOT enable the (currently experimental) address sanitizer flag
 
# Additional References #

 - <https://clang.llvm.org/docs/AddressSanitizer.html>
 - <https://devblogs.microsoft.com/cppblog/asan-for-windows-x64-and-debug-build-support/>
 - <https://github.com/google/sanitizers/wiki/AddressSanitizerWindowsPort>
 
