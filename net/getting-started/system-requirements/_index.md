---
weight: 10
date: "2024-07-29"
author: "Vladimir Lapin"
type: docs
url: /net/system-requirements/
feedback: OCRNET
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

Aspose.OCR for .NET has been tested with the following operating systems:

{{% alert color="primary" %}}
Read [GPU support](#gpu-support) for additional system requirements of the GPU-accelerated package.
{{% /alert %}}

### Desktop

- Microsoft Windows 11: Home, Pro, Pro Education, Pro for Workstations, Enterprise, and Education
- Microsoft Windows 10 version 1703: Home, Professional, Education, and Enterprise
- Microsoft Windows 8: Core, Professional, and Enterprise
- Microsoft Windows 7: Home Premium, Professional, Enterprise, Ultimate
- Microsoft Windows Vista
- macOS
- Linux

### Server

- Microsoft Windows Server 2022
- Microsoft Windows Server 2019
- Microsoft Windows Server 2016
- Microsoft Windows Server 2012
- Microsoft Windows Server 2008 R2 SP1

## Development environments

You can use Aspose.OCR for .NET with any development environment targeting the .NET platform. The library has been specifically tested with the following integrated development environments (IDEs) from Microsoft:

- Microsoft Visual Studio 2015 (update NuGet Package Manager to the latest version)
- Microsoft Visual Studio 2017
- Microsoft Visual Studio 2019
- Microsoft Visual Studio 2022
- Microsoft Visual Studio for Mac version 7.1 or later

## Supported frameworks

Aspose.OCR for .NET supports [.NET Standard 2.0](https://docs.microsoft.com/en-us/dotnet/standard/net-standard?tabs=net-standard-2-0):

.NET implementation	| Supported versions
------------------- | ------------------
.NET | 8.0, 7.0, 6.0, 5.0
.NET Core | 3.1, 3.0, 2.2, 2.1, 2.0
.NET Framework | 4.8, 4.7.2, 4.7.1, 4.7, 4.6.2, 4.6.1
Mono | 6.4, 5.4 
Xamarin.iOS | 12.16, 10.14
Xamarin.Mac | 5.16, 3.8
Xamarin.Android | 10.0, 8.0

{{% alert color="primary" %}} 
Microsoft Visual Studio 2022 [does not support](https://docs.microsoft.com/en-us/visualstudio/releases/2022/compatibility#-visual-studio-2022-support-for-net-development) .NET Core 2.0.
{{% /alert %}} 

## x86 platform support

Aspose.OCR library can work on both x86 and x64 platforms. However, for maximum stability and performance, it is highly recommended to build OCR apps for x64 platforms only.

OCR on x86 platforms is always run in a single thread, even you [explicitly specify](/ocr/net/multithreading/) multiple threads.

{{% alert color="primary" %}} 
Microsoft Visual Studio may not handle upgrades from x86 to x64 versions of the library correctly. To ensure a smooth transition to x64, we recommend creating a new project from scratch or removing and re-adding the Aspose.OCR NuGet package.
{{% /alert %}} 

## External dependencies

- [Microsoft.ML.OnnxRuntime](https://www.nuget.org/packages/Microsoft.ML.OnnxRuntime/) version 1.13.1 or later (for **Aspose.OCR** package only)
- [Microsoft.ML.OnnxRuntime.Gpu](https://www.nuget.org/packages/Microsoft.ML.OnnxRuntime.Gpu/) version 1.7.1 or later (for **Aspose.OCR-GPU** only)
- [System.Drawing.Common](https://www.nuget.org/packages/System.Drawing.Common/) version 4.7.0 or later

{{% alert color="primary" %}} 
These packages are automatically installed when you [install](/ocr/net/installation/) Aspose.OCR / Aspose.OCR-GPU for .NET NuGet package.

You will only need to add these packages if you install Aspose.OCR for .NET using the MSI installer or by manually adding _Aspose.Ocr.dll_ library to the project.
{{% /alert %}} 

## GPU support

GPU-accelerated Aspose.OCR for .NET (**Aspose.OCR-GPU**) has additional system requirements compared to the generic (CPU-based) version of the library:

- The library can only be used on 64-bit operating systems.
- You will need a [CUDA capable GPU](https://developer.nvidia.com/cuda-gpus) and [NVIDIA CUDA Toolkit](https://developer.nvidia.com/cuda-downloads).  
  Read [Installation Guides](https://docs.nvidia.com/cuda/index.html#installation-guides) to learn how to install and check for correct operation of the **CUDA Development Tools** on your system.
