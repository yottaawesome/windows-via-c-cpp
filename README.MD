# Windows via C/C++ 5th edition source code

## Introduction

This is an unofficial source code repo for [Jeffrey Richter](https://twitter.com/jeffrichter) and [Christophe Nasarre's](https://mvp.microsoft.com/en-us/PublicProfile/5003325) [Windows via C/C++ 5th edition](https://www.amazon.com/Windows-via-softcover-Developer-Reference/dp/0735663777). No representation is made that the source code belongs to me, it's simply reproduced here for convenience (so you don't need to dig up the physical media of the book) and remains the copyright of Jeffrey Richter and Christophe Nasarre.

## Building

You'll need Visual Studio 2022 with the _Desktop development with C++_ workload installed. Some samples use MFC, so you'll need to install the _C++ MFC for latest v143 build tools (x86 & x64)_ Visual Studio component to build them (MFC is not installed by default in newer versions of Visual Studio). You should then be able to open any of the VS solution files and build them. It may be possible to open the VS solution files using older (but still modern) versions of Visual Studio, but I've not tested this.

## Changes

The source code has been updated to use VS 2022 (any edition), retargeted to the latest Windows SDK, and to fix a compilation error. The original untouched VS files that came with the book's CD can be found in earlier commits. Older but still modern versions of VS may still be able to open the solution files, but I've not tested this.

## Considerations

All samples still function (as of the time of this writing), but some samples may generate deprecation and security warnings upon compilation, and I recommend you heed those warnings if you intend to use any code in production. Remember this is decades old Win32 code -- depending on what you're trying to do, more modern approaches such as [the C++ standard library](https://en.cppreference.com/w/cpp/header), [C++/WinRT](https://learn.microsoft.com/en-us/windows/uwp/cpp-and-winrt-apis/), [wxWidgets](https://www.wxwidgets.org/), [Boost](https://www.boost.org/), or [POCO C++](https://pocoproject.org/) may be more appropriate.

When using any Win32 code from this repo in production, don't simply copy-paste code; consult the book to understand the code and also review the [Windows API Index](https://docs.microsoft.com/en-us/windows/win32/apiindex/windows-api-list) for relevant and updated API usage notes. It's important to note that this book was written pre-Windows 10 (which, alongside Windows 11, changed a lot about Windows), so while it's still an invaluable resource to learn from, some parts of it may no longer reflect Windows' actual internal functionality.

### Considerations for specific samples

* `JobLab`: On Windows 8 and above, the sample terminates early due to the initial `IsProcessInJob()` check detecting the process is in a job. This check can be disabled on Windows 8 and above, as the rules around processes and jobs were changed starting in Windows 8. See my [comment](https://github.com/yottaawesome/windows-via-c-cpp/blob/master/src/05-JobLab/JobLab.cpp) and this [issue](https://github.com/yottaawesome/windows-via-c-cpp/issues/1) for further information.

## Additional resources

* [Build desktop Windows apps using the Win32 API](https://docs.microsoft.com/en-us/windows/win32/)
* [Get Started with Win32 and C++](https://docs.microsoft.com/en-us/windows/win32/learnwin32/learn-to-program-for-windows)
* [Windows API Index](https://docs.microsoft.com/en-us/windows/win32/apiindex/windows-api-list)
* [COM and ATL](https://docs.microsoft.com/en-us/cpp/atl/introduction-to-com-and-atl?view=msvc-160)
* [C++/WinRT](https://docs.microsoft.com/en-us/windows/uwp/cpp-and-winrt-apis/)
* [Charles Petzold's legendary Programming Windows 5th edition](http://www.charlespetzold.com/pw5/). [Source code repo here](https://github.com/yottaawesome/programming-windows-5th-edition).
* [Microsoft's classic Windows samples](https://github.com/microsoft/Windows-classic-samples)
* [ZetCode's Windows API tutorial](https://zetcode.com/gui/winapi/)
