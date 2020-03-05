# Windows via C/C++ 5th edition source code

## Introduction

This is an unofficial source code repo for Jeffrey Richter and Christophe Nasarre's [Windows via C/C++ 5th edition](https://www.amazon.com/Windows-via-softcover-Developer-Reference/dp/0735663777). The source code is presented here for convenience (so you don't need to dig up the physical media of the book) and remains the copyright of the book authors.

## Changes

The source code has been updated to use VS 2019 Community Edition, retargeted to the latest Windows SDK, and to fix a compilation error. The original untouched VS files that came with the book's CD can be found in earlier commits. 

## Considerations

All samples still function (as of the time of this writing), but some samples may generate deprecation and security warnings upon compilation, and I recommend you heed those warnings if you intend to use any code in production. Remember this is decades old Win32 code -- depending on what you're trying to do, more modern approaches such as [C++/WinRT](https://docs.microsoft.com/en-us/archive/msdn-magazine/2017/january/c-introducing-c-winrt), [wxWidgets](https://www.wxwidgets.org/), [Boost](https://www.boost.org/), or [POCO C++](https://pocoproject.org/) may be more appropriate.

When using any Win32 code from this repo in production, always consult the [Windows API Index](https://docs.microsoft.com/en-us/windows/win32/apiindex/windows-api-list) for relevant and updated API usage notes. Remember that this book was written pre-Windows 10 (which changed a lot about Windows), so some parts of it may no longer reflect Windows' actual internal functionality.

### Considerations for specific samples

* `JobLab`: On Windows 8 and above, the sample terminates early due to the initial `IsProcessInJob()` check detecting the process is in a job. This check can be disabled on Windows 8 and above, as the rules around processes and jobs were changed starting in Windows 8. See my [comment](https://github.com/yottaawesome/windows-via-c-cpp/blob/master/src/05-JobLab/JobLab.cpp) and this [issue](https://github.com/yottaawesome/windows-via-c-cpp/issues/1) for further information.

## Additional resources

* [Build desktop Windows apps using the Win32 API](https://docs.microsoft.com/en-us/windows/win32/)
* [Get Started with Win32 and C++](https://docs.microsoft.com/en-us/windows/win32/learnwin32/learn-to-program-for-windows)
* [Windows API Index](https://docs.microsoft.com/en-us/windows/win32/apiindex/windows-api-list)
