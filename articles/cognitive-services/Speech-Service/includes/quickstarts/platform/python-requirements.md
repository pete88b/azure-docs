---
author: eric-urban
ms.service: cognitive-services
ms.topic: include
ms.date: 06/10/2022
ms.author: eur
---

The Speech SDK for Python is compatible with Windows, Linux, and macOS.

# [Windows](#tab/windows)

On Windows, you can use the x64 or x86 target architecture.

You must install the [Microsoft Visual C++ Redistributable for Visual Studio 2015, 2017, 2019, or 2022](/cpp/windows/latest-supported-vc-redist?view=msvc-170&preserve-view=true) for your platform. Installing this package for the first time might require a restart.

# [Linux](#tab/linux)

The Speech SDK for Python only supports **Ubuntu 18.04/20.04/22.04**, **Debian 9/10/11**, **Red Hat Enterprise Linux (RHEL) 8**, and **CentOS 8** on the x64 architecture when used with Linux. 

[!INCLUDE [Linux distributions](linux-distributions.md)]

# [macOS](#tab/macos)

A macOS version 10.14 or later is required.

---

Install a version of [Python from 3.7 to 3.10](https://www.python.org/downloads/). To check your installation, open a terminal and run the command `python --version`. If it's installed properly, you'll get a response like "Python 3.8.2".

> [!IMPORTANT]
> Make sure that packages of the same platform (x64 or x86) are installed. For example, if you install the x64 redistributable package, then you need to install the x64 Python package. 