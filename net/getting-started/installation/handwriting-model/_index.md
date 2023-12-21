---
weight: 30
date: "2023-12-21"
author: "Vladimir Lapin"
type: docs
url: /net/handwriting-model/
feedback: OCRNET
title: Installing handwriting OCR model
description: Adding or updating Aspose.OCR for .NET recognition model for extracting handwritten texts in your project.
keywords:
- install
- update
- NuGet
- package
- handwriting
- writing
- note
- memo
---

Starting with Aspose.OCR for .NET version **23.12.0** we introduce a specialized recognition model for extracting handwritten text from images. It [supports](/ocr/net/recognition-languages/#supported-handwritten-characters) a number of European languages based on Extended Lain alphabet.

Since the NuGet package has a size limitation of 250MB, this recognition model is implemented as separate package, [Aspose.OCR.Models.Handwritten](https://www.nuget.org/packages/Aspose.OCR.Models.Handwritten). You can use Aspose.OCR for .NET without this package, however you will not be able to use handwritten text recognition and related features.

{{% alert color="caution" %}} 
**Important considerations:**

- Handwriting recognition model cannot be used separately from the core [Aspose.OCR for .NET package](/ocr/net/installation/).
- [Downloadable](/ocr/net/installation/#downloadable) Aspose.OCR for .NET already includes the handwriting recognition model. There is no need to install an additional package.
{{% /alert %}}

The package can be added to your project directly from Microsoft Visual Studio or using PowerShell commands.

## Using NuGet Package Manager UI

**NuGet Package Manager UI** is the easiest way to install and update **Aspose.OCR.Models.Handwritten** in your project.

{{% alert color="primary" %}} 
The instructions below describe how to install or update Aspose.OCR.Models.Handwritten in **Microsoft Visual Studio Community 2019**. The installation process for [other versions](/ocr/net/system-requirements/) of Visual Studio should be quite similar; refer to [documentation](https://docs.microsoft.com/en-us/previous-versions/visualstudio/) for specific details.
{{% /alert %}}

### Installing

1. Open your solution or a project in Microsoft Visual Studio.
2. [Install](/ocr/net/installation/) Aspose.OCR package (either CPU-based or GPU-accelerated).
3. Click **Project** menu and select **Manage NuGet Packages**.  
   Alternatively, you can right-click the project in **Solution Explorer** and select **Manage NuGet Packages** from the context menu.
4. Switch to **Browse** tab.
5. Type "_Aspose.OCR.Models.Handwritten_" (without quotes) in the search box.
6. Click **Install** button.  
   You can select a specific version to be installed. However, it is recommended to always use the latest version for new projects.
7. If prompted, confirm changes to the solution.
8. If prompted, accept the license terms for installed packages.

### Updating

{{% alert color="primary" %}} 
Refer to Aspose.OCR for .NET [Release Notes](/ocr/net/release-notes/) to check if the update might alter the application behavior or require changes to existing code.
{{% /alert %}} 

1. Open your solution or a project in Microsoft Visual Studio.
2. Click **Project** menu and click **Manage NuGet Packages**.  
   Alternatively, you can right-click the project in **Solution Explorer** and select **Manage NuGet Packages** from the context menu.
3. Select **Aspose.OCR.Models.Handwritten** package from the list.
4. Select the update version and click **Update** button.
5. If prompted, confirm changes to the solution.
6. If prompted, accept the license terms for update packages.

## Using NuGet Package Manager Console

**NuGet Package Manager Console** lets you install and update Aspose.OCR.Models.Handwritten in your project using PowerShell commands.

### Installing

1. Open your solution or a project in Microsoft Visual Studio.
2. Click **Tools** menu, select **NuGet Package Manager** and click **Package Manager Console**.
3. Execute the command `Install-Package Aspose.OCR.Models.Handwritten` to install the latest version of **Aspose.OCR.Models.Handwritten** NuGet package.

### Updating

{{% alert color="primary" %}} 
Refer to Aspose.OCR for .NET [Release Notes](/ocr/net/release-notes/) to check if the update might alter the application behavior or require changes to existing code.
{{% /alert %}} 

1. Open your solution or a project in Microsoft Visual Studio.
2. Click **Tools** menu, select **NuGet Package Manager** and click **Package Manager Console**.
3. Check if there are newer versions available for any installed packages by executing a command `Get-Package -updates`. If an update is available, you will see something like this:

   ```
   Id                                  Versions                                 ProjectName
   --                                  --------                                 -----------
   Aspose.OCR.Models.Handwritten       {23.12.1}                                ConsoleApp1
   ```

4. Update Aspose.OCR.Models.Handwritten to the latest version by executing a command `Update-Package Aspose.OCR.Models.Handwritten`.  
   
   To update to a specific version, provide its name in the `-Version` parameter . For example: `Update-Package Aspose.OCR.Models.Handwritten -Version 23.12.0`.
