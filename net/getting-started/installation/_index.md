---
weight: 20
date: "2022-06-09"
author: "Vladimir Lapin"
type: docs
url: /net/installation/
title: Installation
description: Adding or updating Aspose.OCR for .NET package in your project.
keywords:
- install
- update
- NuGet
- package
- zip
- MSI
- download
---

**Aspose.OCR for .NET** is distributed as a NuGet package or as a [downloadable file](https://downloads.aspose.com/ocr/net).

## NuGet package

Aspose offers two options for **Aspose.OCR for .NET** NuGet package:

- [**Aspose.OCR**](https://www.nuget.org/packages/Aspose.OCR/) - CPU-based OCR;
- [**Aspose.OCR-GPU**](https://www.nuget.org/packages/Aspose.OCR-GPU/) - GPU-accelerated OCR (requires a [CUDA capable GPU](https://developer.nvidia.com/cuda-gpus) and [NVIDIA CUDA Toolkit](https://developer.nvidia.com/cuda-downloads)).

There is no need to download and install any software - the package can be added to your project directly from Microsoft Visual Studio. Both packages are installed and updated in the same way, so they will later be referred as _"Aspose.OCR for .NET"_.

{{% alert color="primary" %}} 
The instructions below describe how to install or update Aspose.OCR for .NET in **Microsoft Visual Studio Community 2019**. The installation process for [other versions](/ocr/net/system-requirements/) of Visual Studio should be quite similar; refer to [documentation](https://docs.microsoft.com/en-us/previous-versions/visualstudio/) for specific details.
{{% /alert %}} 

### Using NuGet Package Manager UI

**NuGet Package Manager UI** is the easiest way to install and update Aspose.OCR for .NET in your project.

#### Installing

1. Open your solution or a project in Microsoft Visual Studio.
2. Click **Project** menu and select **Manage NuGet Packages**.  
   Alternatively, you can right-click the project in **Solution Explorer** and select **Manage NuGet Packages** from the context menu.
3. Switch to **Browse** tab.
4. Type "_Aspose.OCR_" (without quotes) in the search box.
5. Select **Aspose.OCR** or **Aspose.OCR-GPU** package from the list (you only need to install one package).
6. Click **Install** button.  
   You can select a specific version to be installed. However, it is recommended to always use the latest version for new projects.
7. If prompted, confirm changes to the solution.
8. If prompted, accept the license terms for installed packages.

#### Updating

{{% alert color="primary" %}} 

Refer to Aspose.OCR for .NET [Release Notes](/ocr/net/release-notes/) to check if the update might alter the application behavior or require changes to existing code.

{{% /alert %}} 

1. Open your solution or a project in Microsoft Visual Studio.
2. Click **Project** menu and click **Manage NuGet Packages**.  
   Alternatively, you can right-click the project in **Solution Explorer** and select **Manage NuGet Packages** from the context menu.
3. Select **Aspose.OCR** or **Aspose.OCR-GPU** package (depending on your installation option) from the list.
4. Select the update version and click **Update** button.
5. If prompted, confirm changes to the solution.
6. If prompted, accept the license terms for update packages.

### Using NuGet Package Manager Console

**NuGet Package Manager Console** lets you install and update Aspose.OCR for .NET in your project using PowerShell commands.

#### Installing

1. Open your solution or a project in Microsoft Visual Studio.
2. Click **Tools** menu, select **NuGet Package Manager** and click **Package Manager Console**.
3. Execute the command:

    - `Install-Package Aspose.OCR` to install the latest version of **Aspose.OCR** NuGet package.
    - `Install-Package Aspose.OCR-GPU` to install the latest version of GPU-accelerated **Aspose.OCR** NuGet package.

#### Updating

{{% alert color="primary" %}} 

Refer to Aspose.OCR for .NET [Release Notes](/ocr/net/release-notes/) to check if the update might alter the application behavior or require changes to existing code.

{{% /alert %}} 

1. Open your solution or a project in Microsoft Visual Studio.
2. Click **Tools** menu, select **NuGet Package Manager** and click **Package Manager Console**.
3. Checks if there are newer versions available for any installed packages by executing a command `Get-Package -updates`. If an update is available, you will see something like this:

   ```
   Id           Versions   Description                                    ProjectName
   --           --------   -----------                                    -----------
   Aspose.OCR   {22.3.0}   Aspose.OCR for .NET is a standalone OCR API... ConsoleApp1
   ```
4. Update Aspose.OCR for .NET to the latest version by executing a command `Update-Package Aspose.OCR` (if you are using **Aspose.OCR** NuGet package) or `Update-Package Aspose.OCR-GPU` (if you are using GPU-accelerated **Aspose.OCR** NuGet package).  
   
   To update to a specific version, provide its name in the `-Version` parameter . For example: `Update-Package Aspose.OCR -Version 22.5.0`.

## Downloadable

To use a downloaded Aspose.OCR component in your application:

1. Open your solution or a project in Microsoft Visual Studio.
2. Expand the project tree in **Solution Explorer**.
3. Right-click **References** and select **Add COM Reference** (for .NET Core project) or **Add Reference** (for .NET Framework project) from the context menu.
4. Click **Browse...** button and locate _Aspose.OCR.dll_ file.
5. Install the [required dependencies](/ocr/net/system-requirements/#external-dependencies) from NuGet.
6. Click **OK** button.

**Aspose.OCR** will appear under the project's _References_ folder.
