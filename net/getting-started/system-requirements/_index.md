---
weight: 10
date: "2022-06-08"
author: "Vladimir Lapin"
type: docs
url: /net/system-requirements/
title: System requirements
description: Minimum requirements and prerequisites for developing applications with Aspose.OCR for .NET.
keywords:
- prerequisites
- requirements
- framework
- environment
- .NET
---

## Supported operating systems

Both x86 (where applicable) and x64 versions of the following operating systems are supported:

### Desktop

- Windows 11: Home, Pro, Pro Education, Pro for Workstations, Enterprise, and Education
- Windows 10 version 1703: Home, Professional, Education, and Enterprise
- Windows 8: Core, Professional, and Enterprise
- Windows 7: Home Premium, Professional, Enterprise, Ultimate
- Windows Vista
- macOS
- Linux

### Server

- Windows Server 2022
- Windows Server 2019
- Windows Server 2016
- Windows Server 2012
- Windows Server 2008 R2 SP1

## Development environments

You can use Aspose.OCR for .NET with any development environment targeting the .NET platform. The library has been specifically tested with the following integrated development environments (IDEs) from Microsoft:

- Microsoft Visual Studio 2017 version 15.3 or later
- Microsoft Visual Studio 2019
- Microsoft Visual Studio 2022
- Microsoft Visual Studio for Mac version 7.1 or later

## Supported frameworks

Aspose.OCR for .NET supports [.NET Standard 2.0](https://docs.microsoft.com/en-us/dotnet/standard/net-standard?tabs=net-standard-2-0):

.NET implementation	| Supported versions
------------------- | ------------------
.NET | 5.0, 6.0
.NET Core | 2.0, 2.1, 2.2, 3.0, 3.1
.NET Framework | 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2, 4.8
Mono | 5.4, 6.4
Xamarin.iOS | 10.14, 12.16
Xamarin.Mac | 3.8, 5.16
Xamarin.Android | 8.0, 10.0

{{% alert color="primary" %}} 
Microsoft Visual Studio 2022 [does not support](https://docs.microsoft.com/en-us/visualstudio/releases/2022/compatibility#-visual-studio-2022-support-for-net-development) .NET Core 2.0.
{{% /alert %}} 

## External dependencies

- [Microsoft.ML.OnnxRuntime](https://www.nuget.org/packages/Microsoft.ML.OnnxRuntime/) version 1.11.0 or later (for **Aspose.OCR** package only)
- [Microsoft.ML.OnnxRuntime.Gpu](https://www.nuget.org/packages/Microsoft.ML.OnnxRuntime.Gpu/) version 1.7.1 or later (for **Aspose.OCR-GPU** only)
- [System.Drawing.Common](https://www.nuget.org/packages/System.Drawing.Common/) version 4.7.0 or later

{{% alert color="primary" %}} 
These packages are automatically installed when you [install](/ocr/net/installation/) Aspose.OCR / Aspose.OCR-GPU for .NET NuGet package.

You will only need to add these packages if you install Aspose.OCR for .NET using the MSI installer or by manually adding _Aspose.Ocr.dll_ library to the project.
{{% /alert %}} 

## GPU support

To use **Aspose.OCR-GPU** you will need a [CUDA capable GPU](https://developer.nvidia.com/cuda-gpus) and [NVIDIA CUDA Toolkit](https://developer.nvidia.com/cuda-downloads).

Read [Installation Guides](https://docs.nvidia.com/cuda/index.html#installation-guides) to learn how to install and check for correct operation of the **CUDA Development Tools** on your system.
