---
weight: 20
date: "2022-12-07"
author: "Vladimir Lapin"
type: docs
url: /cpp/installation/
feedback: OCRCPP
title: Installation
description: Adding or updating Aspose.OCR for C++ package in your project.
keywords:
- install
- update
- NuGet
- package
- zip
- MSI
- download
---

**Aspose.OCR for C++** is distributed as a NuGet package or as a [downloadable file](https://downloads.aspose.com/ocr/cpp).

## NuGet package

Aspose offers four options for **Aspose.OCR for C++** NuGet package:

- [**Aspose.Ocr.Cpp**](https://www.nuget.org/packages/Aspose.Ocr.Cpp) - CPU-based OCR for Windows;
- [**Aspose.Ocr.Cpp-GPU**](https://www.nuget.org/packages/Aspose.Ocr.Cpp-GPU) - GPU-accelerated OCR for Windows ([requires](/ocr/cpp/installation/gpu/) a CUDA capable GPU and NVIDIA CUDA Toolkit).
- [**Aspose.Ocr.Cpp-Linux**](https://www.nuget.org/packages/Aspose.Ocr.Cpp-Linux) - CPU-based OCR for Linux;
- [**Aspose.Ocr.Cpp-Linux-Gpu**](https://www.nuget.org/packages/Aspose.Ocr.Cpp-Linux-GPU) - GPU-accelerated OCR for Linux ([requires](/ocr/cpp/installation/gpu/) a CUDA capable GPU and NVIDIA CUDA Toolkit).

There is no need to download and install any software - the package and all its dependencies can be added to your project directly from Microsoft Visual Studio. All packages are installed and updated in the same way, so they will later be referred as _"Aspose.OCR for C++"_.

{{% alert color="primary" %}} 
The instructions below describe how to install or update Aspose.OCR for C++ in **Microsoft Visual Studio Community 2019**. The installation process for other versions of Visual Studio should be quite similar; refer to [documentation](https://docs.microsoft.com/en-us/previous-versions/visualstudio/) for specific details.
{{% /alert %}}

### Using NuGet Package Manager UI

**NuGet Package Manager UI** is the easiest way to install and update Aspose.OCR for C++ in your project.

#### Installing

1. Open your solution or a project in Microsoft Visual Studio.
2. Click **Project** menu and select **Manage NuGet Packages**.  
   Alternatively, you can right-click the project in **Solution Explorer** and select **Manage NuGet Packages** from the context menu.
3. Switch to **Browse** tab.
4. Type "_Aspose.Ocr.Cpp_" (without quotes) in the search box.
5. Select the version for the target platform from the list (you only need to install one package).
6. Click **Install** button.  
   You can select a specific version to be installed. However, it is recommended to always use the latest version for new projects.
7. If prompted, confirm changes to the solution.
8. If prompted, accept the license terms for installed packages.

#### Updating

{{% alert color="primary" %}} 
Refer to Aspose.OCR for C++ [Release Notes](/ocr/cpp/release-notes/) to check if the update might alter the application behavior or require changes to existing code.
{{% /alert %}} 

1. Open your solution or a project in Microsoft Visual Studio.
2. Click **Project** menu and click **Manage NuGet Packages**.  
   Alternatively, you can right-click the project in **Solution Explorer** and select **Manage NuGet Packages** from the context menu.
3. Select Aspose.OCR for C++ package (depending on your installation option) from the list.
4. Select the update version and click **Update** button.
5. If prompted, confirm changes to the solution.
6. If prompted, accept the license terms for update packages.

### Using NuGet Package Manager Console

**NuGet Package Manager Console** lets you install and update Aspose.OCR for C++ in your project using PowerShell commands.

#### Installing

1. Open your solution or a project in Microsoft Visual Studio.
2. Click **Tools** menu, select **NuGet Package Manager** and click **Package Manager Console**.
3. Execute the command:

    - `Install-Package Aspose.Ocr.Cpp` to install the latest version of **Aspose.OCR** NuGet package for Windows.
    - `Install-Package Aspose.Ocr.Cpp-GPU` to install the latest version of GPU-accelerated **Aspose.OCR** NuGet package for Windows.
    - `Install-Package Aspose.Ocr.Cpp-Linux` to install the latest version of **Aspose.OCR** NuGet package for Linux.
    - `Install-Package Aspose.Ocr.Cpp-Linux-Gpu` to install the latest version of GPU-accelerated **Aspose.OCR** NuGet package for Linux.

#### Updating

{{% alert color="primary" %}} 
Refer to Aspose.OCR for C++ [Release Notes](/ocr/cpp/release-notes/) to check if the update might alter the application behavior or require changes to existing code.
{{% /alert %}} 

1. Open your solution or a project in Microsoft Visual Studio.
2. Click **Tools** menu, select **NuGet Package Manager** and click **Package Manager Console**.
3. Checks if there are newer versions available for any installed packages by executing a command `Get-Package -updates`. If an update is available, you will see something like this:

   ```
   Id               Versions   Description                             ProjectName
   --               --------   -----------                             -----------
   Aspose.OCR.Cpp   {22.9.0}   Aspose.OCR for C++ is a powerful yet... ConsoleApp1
   ```
4. Update Aspose.OCR for C++ to the latest version by executing a command `Update-Package [package name]` (depending on your platform).  
   
   To update to a specific version, provide its name in the `-Version` parameter . For example: `Update-Package Aspose.OCR.Cpp -Version 22.9.0`.

## Downloadable

To use a downloaded Aspose.OCR component in your application:

1. Extract the downloadable package.
2. Copy **lib** and **include** folders into your project.
3. Add **Aspose.Ocr.Cpp.lib** dependency to your project.
4. Add **lib/x64** folder to **Additional Library Directories** of your project.
5. Add the path to **include** folder to **Additional Include Directories** of your project.
6. Install the [required dependencies](/ocr/cpp/system-requirements/#external-dependencies) to your project.
7. Add `#include "aspose_ocr.h"` in your code.
