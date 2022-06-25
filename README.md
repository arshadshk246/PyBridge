# PyBridge 2.0
###### Last repository update: 25/06/2022

> **WARNING NOTE**:
>> The use of this version of PyBridge is not recommended YET. It's in update process and soon will be available for download.
<br>If you want to contribute to this repository, send your pull request to the code on [Official PyBridge Repository](https://www.github.com/hbisneto/PyBridge)

## Update Logs (Released Versions)

```
PyBridge 2.0:

• Added new native library: time
• Added Module "system" to PyBridge
• Added Library "Logs.py" to "system" module
• Added Library "Requirements.py" to "system" module
• Added Backup reference to FileSystem.py
• Added Samples reference to FileSystem.py
• Added .gitignore to projects created by PyBridge
• Added .gitignore to PyBridge
• Updated modules and libraries to improve system ("SystemRequirements.py" is deprecated. Use "Requirements.py" instead)
1. Renamed Module "ErrorReport" to "exception"
2. Renamed Module "Linux" to "linux"
3. Renamed Module "Mac" to "mac"
4. Renamed Module "Windows" to "windows"
• Projects create using PyBridge will follow PyBridge FileSystem standards (See "Structure of Projects Created by PyBridge" in README.MD file in the root of project)
• Added ability to download more sample codes
• Improvements in "Download Samples" feature
```

#

<br>

With PyBridge it is possible to run Python scripts by bridging the code implemented in the project created with other platforms.

With PyBridge it is possible to create scripts that will run on:

1. **Linux**;
2. **macOS**;
3. **Windows**;

**PyBridge is a program entirely developed in Python. To run the program, open the `PyBridge.py` file located at the root of this project.**

> Note:
>> PyBridge was born from Python 3.9. For this reason, the same version of Python (version 3.9) or higher is recommended to run the system.

PyBridge has a standard ***error handling*** library that can run in any environment. Every method implemented within the library can be called from any part of the code. That way, it is not necessary to implement the ```raise RuntimeError()``` exception call inside the program's runtime library. Just import the module and reference the function call according to the treatment that must be executed.

> Note: Read more about the `ErrorReport` module in **PyBridge Modules** below.

#

## PyBridge Modules

The following modules are part of PyBridge:

* **ErrorReport:** The module contains two files with the purpose of raising errors generated by the program, in addition to checking minimum requirements for execution.
    - **ErrorList.py**: This library contains events that are raised when the program execution needs to be interrupted.
    - **SystemRequirements.py**: This library is used to check if the system complies with the minimum requirements to run.

* **Linux:** The module contains four libraries organized to run the program in a Linux environment
    - **Linux.py**: Codes implemented in this library will be executed before the Main Script.
    - **LinuxApp.py**: This library is used to implement code that will run in the Linux environment
    - **FileSystem.py**: This library contains default directories in Linux environments
    - **SplashScreen.py**: This library contains information about your project

* **Mac:** The module contains four libraries organized to run the program on macOS
    - **Mac.py**: Codes implemented in this library will be executed before the Main Script.
    - **MacApp.py**: This library is used to implement code that will run on macOS
    - **FileSystem.py**: This library contains standard macOS directories
    - **SplashScreen.py**: This library contains information about your project

* **Windows:** The module contains four libraries organized to run the program on Windows
    - **Windows.py**: Codes implemented in this library will be executed before the Main Script.
    - **WindowsApp.py**: This library is used to implement code that will run on Windows
    - **FileSystem.py**: This library contains standard Windows directories
    - **SplashScreen.py**: This library contains information about your project

#

## Sample Programs

Below is a list of examples of Python programs created using PyBridge

- **GetInfo:** Get the filename, creation date and modification date of a file anywhere, on any platform.
<br>[GetInfo: PyBridge Sample Application](https://github.com/hbisneto/GetInfo/)

- **JoKenPo:** Famous game known as "Rock, Paper and Scissors".
<br>[JoKenPo: PyBridge Sample Application](https://github.com/hbisneto/JoKenPo)

#

## Analysis of the Created Bridge

### Hello World

Below is a detailed example of running a `Hello World` program created by PyBrigde on `Windows`

**Program running:**

```
Name: Hello World
Version: 1.0
Created By: YOU
Copyright © 2021 | YOU All rights reserved.
==================================================
[Hello World for Windows] - Running...
==================================================

Hello World!
```
**Execution Analysis:**

```
### Load imported libraries into Windows.py
# Load SplashScreen
Name: Hello World
Version: 1.0
Created By: YOU
Copyright © 2021 | YOU All rights reserved.
==================================================
[Hello World for Windows] - Running...
==================================================
# End of SplashScreen
# Load SystemRequirements
# End of SystemRequirements
# Load WindowsApp
Hello World!
```

#

### Hello World (Requires Python 3.9)

Below is a detailed example of running a `Hello World` program created by PyBrigde with the Python 3.9 requirement on `Mac`

**Program running:**

```
Name: Hello World
Version: 1.0
Created By: YOU
Copyright © 2021 | YOU All rights reserved.
================================================== 
[Hello World for Mac] - Running...
==================================================

Traceback (most recent call last):
  File "/Users/YOU/Documents/PyBridge/Projects/Hello World/__init__.py", line 31, in <module>
    Main()
  File "/Users/YOU/Documents/PyBridge/Projects/Hello World/__init__.py", line 24, in Main
    Mac.Mac()
  File "/Users/YOU/Documents/PyBridge/Projects/Hello World/Mac/Mac.py", line 16, in Mac
    from ErrorReport import SystemRequirements
  File "/Users/YOU/Documents/PyBridge/Projects/Hello World/ErrorReport/SystemRequirements.py", line 34, in <module>
    ErrorList.Raise().Requirements().MajorVersion(CurrentVersion, TargetVersion, TargetMajor)
  File "/Users/YOU/Documents/PyBridge/Projects/Hello World/ErrorReport/ErrorList.py", line 7, in MajorVersion
    raise Exception(f'>> You cannot run the application because it requires Python {TargetVersion} or later. [Current Version: {CurrentVersion}]')
Exception: >> You cannot run the application because it requires Python 3.9.0 or later. [Current Version: 3.6.0]
```
**Execution Analysis:**

```
### Load imported libraries into Mac.py
# Load SplashScreen
Name: Hello World
Version: 1.0
Created By: YOU
Copyright © 2021 | YOU All rights reserved.
==================================================
[Hello World for Mac] - Running...
==================================================
# End of SplashScreen
# Load SystemRequirements

Traceback (most recent call last):
  File "/Users/YOU/Documents/PyBridge/Projects/Hello World/__init__.py", line 31, in <module>
    Main()
  File "/Users/YOU/Documents/PyBridge/Projects/Hello World/__init__.py", line 24, in Main
    Mac.Mac()
  File "/Users/YOU/Documents/PyBridge/Projects/Hello World/Mac/Mac.py", line 16, in Mac
    from ErrorReport import SystemRequirements
  File "/Users/YOU/Documents/PyBridge/Projects/Hello World/ErrorReport/SystemRequirements.py", line 34, in <module>
    ErrorList.Raise().Requirements().MajorVersion(CurrentVersion, TargetVersion, TargetMajor)
  File "/Users/YOU/Documents/PyBridge/Projects/Hello World/ErrorReport/ErrorList.py", line 7, in MajorVersion
    raise Exception(f'>> You cannot run the application because it requires Python {TargetVersion} or later. [Current Version: {CurrentVersion}]')
Exception: >> You cannot run the application because it requires Python 3.9.0 or later. [Current Version: 3.6.0]
```

#

## Native Libraries

The following libraries were used to implement the tool:

* **codecs:** The module defines functions for encoding and decoding with any codec.
    - Read more about the ```codecs``` library at [codecs — Codec registry and base classes](https://docs.python.org/3.9/library/codecs.html)

* **datetime:** The ```datetime``` module provides the classes for handling dates and times.
    - Read more about the ```datetime``` library at [datetime — Basic date and time types](https://docs.python.org/3.9/library/datetime.html)

* **getpass:** Portable password input.
    - Read more about the ```getpass``` library at [getpass — Portable Password Input](https://docs.python.org/3.9/library/getpass.html)

* **os:** This module provides a simple way to use functionality that is OS dependent.
    - Read more about the ```os``` library at [os — Miscellaneous operating system interfaces](https://docs.python.org/3.9/library/os.html)

* **pathlib:** This module offers classes representing filesystem paths with semantics appropriate for different operating systems. Path classes are divided between pure paths, which provide purely computational operations without I/O, and concrete paths, which inherit from pure paths but also provide I/O operations.
    - Read more about the ```pathlib``` library at [pathlib — Object-oriented filesystem paths](https://docs.python.org/3.9/library/pathlib.html)

* **shutil:** The shutil module provides several high-level operations on files and file collections. In particular, functions are provided that support copying and removing files. For operations on individual files, see also the **os** module.
    - Read more about the ```shutil``` library at [shutil — High-level file operations](https://docs.python.org/3.9/library/shutil.html)

* **sys:** This module provides access to some variables used or maintained by the interpreter and functions that interact strongly with the interpreter.
    - Read more about the ```sys``` library at [sys — System-specific parameters and functions](https://docs.python.org/3.9/library/sys.html)

* **time:** This module provides various time-related functions. For related functionality, see also the [datetime](https://docs.python.org/3.9/library/datetime.html) and [calendar](https://docs.python.org/3.9/library/calendar.html) modules.
    - Read more about the ```time``` library at [time — Time access and conversions](https://docs.python.org/3.9/library/time.html)

* **zipfile:** The ZIP file format is a common archive and compression standard. This module provides tools to create, read, write, append, and list a ZIP file. Any advanced use of this module will require an understanding of the format, as defined in [PKZIP Application Note](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT).
    - Read more about the ```zipfile``` library at [zipfile — Work with ZIP archives](https://docs.python.org/3.9/library/zipfile.html)

#

## Third Party Libraries

The following libraries were used to implement the tool:

* **tweepy:** An easy-to-use library for accessing the Twitter API.
    - Read more about the ```tweepy``` library at [tweepy — An easy-to-use Python library for accessing the Twitter API](https://docs.tweepy.org/en/stable/)

> The use of the tweepy library is optional and only mandatory in cases of "Twitter Application Project" created in PyBridge.

#

* **requests:** Requests is an elegant and simple HTTP library for Python, built for human beings.
    - Read more about the ```requests``` library at [Requests: HTTP for Humans™](https://docs.python-requests.org/en/latest/)

> The use of the requests library is mandatory in cases of "Download Sample Projects" on PyBridge.

#

## Structure of Projects Created by PyBridge

* **Blank Project** & **Menu Application Loop Project:** The following example shows the structure of the ```Hello_World``` project created by PyBridge.

```
.
├── __init__.py
├── ErrorReport
│ ├── ErrorList.py
│ └── SystemRequirements.py
├── Linux
│ ├── Linux.py
│ ├── LinuxApp.py
│ ├── FileSystem.py
│ └── SplashScreen.py
├── Mac
│ ├── Mac.py
│ ├── MacApp.py
│ ├── FileSystem.py
│ └── SplashScreen.py
├── Windows
│ ├── Windows.py
│ ├── WindowsApp.py
│ ├── FileSystem.py
│ └── SplashScreen.py
└── README.md
```

* **Twitter Application Project:** The following example shows the structure of the ```MyTweets``` project created by Pybridge:

```
.
├── __init__.py
├── ErrorReport
│ ├── ErrorList.py
│ └── SystemRequirements.py
├── Linux
│ ├── Linux.py
│ ├── LinuxApp.py
│ ├── FileSystem.py
│ └── SplashScreen.py
├── Mac
│ ├── Mac.py
│ ├── MacApp.py
│ ├── FileSystem.py
│ └── SplashScreen.py
├── Windows
│ ├── Windows.py
│ ├── WindowsApp.py
│ ├── FileSystem.py
│ └── SplashScreen.py
├── Tokens.py
└── README.md
```

#

## Update Logs (Released Versions)

For more information about update logs, access [RELEASES](https://github.com/hbisneto/PyBridge/releases) page on this repository.

# Contribute to this repository:

- If you found any error and can send the correction, I'll thank you immensely!
- If you have any ideas, send them to me.
- If you have any questions about something, ask.
- Contribute!

#

Copyright © 2021–2022 Heitor Bisneto. All rights reserved.
