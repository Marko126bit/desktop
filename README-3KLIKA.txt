# SPDX-FileCopyrightText: 2025 Nextcloud GmbH and Nextcloud contributors
# SPDX-License-Identifier: GPL-2.0-or-later

3Klika Oblak Windows Build Instructions
=======================================

Prerequisites
-------------
* Microsoft Visual Studio 2022 with the Desktop development with C++ workload.
* Qt 6.8.0 for MSVC 2022 (64-bit) installed and the `qt-cmake` integration available in your PATH.
* Ninja build system available in your PATH.
* OpenSSL 3 runtime libraries accessible to the build (see the official Nextcloud desktop build guide for details).

Configure
---------
```powershell
mkdir build-win64
cd build-win64
cmake -G Ninja ^
  -DCMAKE_BUILD_TYPE=Release ^
  -DCMAKE_PREFIX_PATH="C:/Qt/6.8.0/msvc2022_64" ^
  ..
```

Build
-----
```powershell
cmake --build .
```

Package (optional)
------------------
Invoke CPack if you need an installer package:
```powershell
cpack
```

Client defaults
---------------
The rebranded client is preconfigured to connect exclusively to the 3Klika cloud service:
```
lastConnectedServer=https://oblak.3klika.rs
```
