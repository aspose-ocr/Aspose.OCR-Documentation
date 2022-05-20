---
title: System Requirements
type: docs
weight: 70
url: /net/system-requirements/
---

## **Supported Operating Systems**
### **Windows**

- Microsoft Windows 2008 R2 SP1, 2008 SP2 Server ( x64 )
- Microsoft Windows 2012, 2012 R2 Server ( x64 )
- Microsoft Windows Vista ( x64 )
- Microsoft Windows 8, 8.1 ( x64 )
- Microsoft Windows 10 ( x64, x86, AnyCPU )
- Mac OS X
- Linux

## **Supported Frameworks**

** - .NET Standard 2.0** ( supports https://docs.microsoft.com/en-us/dotnet/standard/net-standard)

## **Dependencies CPU version**
 - Microsoft.ML.OnnxRuntime   Version="1.7.0"
 - System.Drawing.Common  Version="4.7.0"

Notice: if you install a package from Nuget, you don't need to install any additionals (as for .core as for .framework). If you install Aspose.Ocr from MSI installer or simply want to use Aspose.Ocr.dll,
you will need to:

    1. add a reference on Aspose.Ocr.dll
	
    2. install from Nuget Microsoft.ML.OnnxRuntime   Version="1.7.0" and System.Drawing.Common  Version="4.7.0"

## **Dependencies GPU version**
 - Microsoft.ML.OnnxRuntime.Gpu  Version="1.7.1"
 - System.Drawing.Common  Version="4.7.0"

## **Development Environments**

You can use Aspose.OCR for .NET to develop applications in any development environment that targets the .NET platform, but the following environments are explicitly supported:

 - Microsoft Visual Studio 2017 from version 15.3
 - Microsoft Visual Studio 2019
 - Microsoft Visual Studio for Mac from version 7.1

## **GPU version**
If you want to use Aspose.OCR-GPU you have to make sure does your GPU supports CUDA.  You can do this by link https://developer.nvidia.com/cuda-gpus. 
To use CUDA on your system, you will need the following installed:

 - A CUDA-capable GPU
 - A supported version of Microsoft Windows
 - A supported version of Microsoft Visual Studio
 - the NVIDIA CUDA Toolkit (available at http://developer.nvidia.com/cuda-downloads)
 
Installation guide for CUDA you can find by link https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/index.html
