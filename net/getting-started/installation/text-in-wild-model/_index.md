---
weight: 20
date: "2023-10-12"
author: "Vladimir Lapin"
type: docs
url: /net/text-in-wild-model/
feedback: OCRNET
title: Installing Text-in-wild OCR model
description: Adding or updating Aspose.OCR for .NET Text-in-wild recognition model in your project.
keywords:
- install
- update
- NuGet
- package
- text-in-wild
- street photo
---

Starting with Aspose.OCR for .NET version **23.10.0** we introduce a specialized recognition model for extracting content from street photos and other images with sparse text and noisy/colored backgrounds.

Since the NuGet package has a size limitation of 250MB, this recognition model is implemented as separate package, [Aspose.OCR.Models.TextInWild](https://www.nuget.org/packages/Aspose.OCR.Models.TextInWild). You can use Aspose.OCR for .NET without this package, however you will not be able to use the methods and properties that depend on Text-in-wild OCR model.

{{% alert color="caution" %}} 
**Important considerations:**

- Text-in-wild recognition model cannot be used separately from the core [Aspose.OCR for .NET package](/ocr/net/installation/).
- [Downloadable](/ocr/net/installation/#downloadable) Aspose.OCR for .NET already includes the Text-in-wild recognition model. There is no need to install an additional package.
{{% /alert %}}

The package can be added to your project directly from Microsoft Visual Studio or using PowerShell commands.

## Using NuGet Package Manager UI

**NuGet Package Manager UI** is the easiest way to install and update **Aspose.OCR.Models.TextInWild** in your project.

{{% alert color="primary" %}} 
The instructions below describe how to install or update Aspose.OCR.Models.TextInWild in **Microsoft Visual Studio Community 2019**. The installation process for [other versions](/ocr/net/system-requirements/) of Visual Studio should be quite similar; refer to [documentation](https://docs.microsoft.com/en-us/previous-versions/visualstudio/) for specific details.
{{% /alert %}}

### Installing

1. Open your solution or a project in Microsoft Visual Studio.
2. [Install](/ocr/net/installation/) Aspose.OCR package (either CPU-based or GPU-accelerated).
3. Click **Project** menu and select **Manage NuGet Packages**.  
   Alternatively, you can right-click the project in **Solution Explorer** and select **Manage NuGet Packages** from the context menu.
4. Switch to **Browse** tab.
5. Type "_Aspose.OCR.Models.TextInWild_" (without quotes) in the search box.
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
3. Select **Aspose.OCR.Models.TextInWild** package from the list.
4. Select the update version and click **Update** button.
5. If prompted, confirm changes to the solution.
6. If prompted, accept the license terms for update packages.

## Using NuGet Package Manager Console

**NuGet Package Manager Console** lets you install and update Aspose.OCR.Models.TextInWild in your project using PowerShell commands.

### Installing

1. Open your solution or a project in Microsoft Visual Studio.
2. Click **Tools** menu, select **NuGet Package Manager** and click **Package Manager Console**.
3. Execute the command `Install-Package Aspose.OCR.Models.TextInWild` to install the latest version of **Aspose.OCR.Models.TextInWild** NuGet package.

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
   Aspose.OCR.Models.TextInWild        {23.10.0}                                ConsoleApp1
   ```

4. Update Aspose.OCR.Models.TextInWild to the latest version by executing a command `Update-Package Aspose.OCR.Models.TextInWild`.  
   
   To update to a specific version, provide its name in the `-Version` parameter . For example: `Update-Package Aspose.OCR.Models.TextInWild -Version 23.10.0`.
