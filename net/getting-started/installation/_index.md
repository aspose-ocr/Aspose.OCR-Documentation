---
title: Installation
type: docs
weight: 80
url: /net/installation/
---
## **Windows**

## **Installing Aspose.OCR for .NET through NuGet**

NuGet is the easiest way to download and install Aspose .NET APIs. **Open** Microsoft Visual Studio. Select **TOOLS** menu, goto **NuGet Package Manager** and select **Manage NuGet packages for solution**. Search 'aspose.ocr' keyword. This will find the desired Aspose API. Click on "Install" button, the selected API will be downloaded and referenced in your project.

For .NET you can choose Aspose.OCR and Aspose.OCR-GPU versions. Notice that GPU version requires CUDA in your system
![todo:image_alt_text](ex1.bmp)

## **Install or Update Aspose.OCR using the Package Manager Console**

You can follow the steps below to install or upgrad the Aspose.OCR API using the package manager console:
Open your solution/project in Visual Studio.
Select **TOOLS** -> **NuGet Package Manager** -> **Package Manager Console** from the top menu. This will open package manager console.

![todo:image_alt_text](installation_2.png)

Type the command `“Install-Package Aspose.OCR -Version x.x.0”` and press enter to install latest full release into your application. Alternatively, you can add the "-prerelease" suffix to the command in order to specify that the latest release including hot fixes is to be installed as well.

![todo:image_alt_text](installation_3.jpg)

If you are not familiar with the Aspose EULA <https://company.aspose.com/legal/eula> then it is a good idea to read the license referenced in the URL. 
You should now find that Aspose.OCR has successfully been added and referenced in your application for you.

![todo:image_alt_text](installation_4.jpg)

In the package manager console, you can use the command `Update-Package Aspose.OCR` and press enter to check for any updates to the Aspose.OCR package and install them if present. You can also add the "-prerelease" suffix to update latest release.

## **Referencing the Component**

To use any component in your application, you must add a reference to it. The following steps assume that you use Visual Studio .NET.

1. In Solution Explorer, expand the project node you want to add a reference to.
2. Right-click the project’s References node and select Add COM Reference (for .core project)  or Add Reference (for .framework project) from the menu.
3. In the Add Reference dialog, select the .NET tab (selected by default).
4. If you have used an MSI installer to install Aspose.OCR or if you have downloaded and unpacked the DLL only, locate the Aspose.OCR.dll file using the Browse button. Now that you have referenced Aspose.OCR and it should appear in the Selected Components pane of the dialog box.
5. Additionally, you have to install dependencies packages from nuget (for example for Aspose.OCR 21.8.0 version you have to install Microsoft.ML.OnnxRuntime 1.7.0 and System.Drawing.Common 4.7.0.
6. Notice that GPU version requires CUDA in your system.
7. Click OK.

The Aspose.OCR reference appears under the project's References node.

## **Uninstalling Aspose.OCR for .NET**

If you have used an MSI installer to deploy Aspose.OCR, follow these steps to completely remove the component and the associated demos and documentation:

1. From the **Start** menu, select **Settings** | **Control Panel**.
1. Click **Add/Remove Programs**.
1. Select **Aspose.OCR**.
1. Click the **Change/Remove** button to remove Aspose.OCR.

The component is un-installed.
