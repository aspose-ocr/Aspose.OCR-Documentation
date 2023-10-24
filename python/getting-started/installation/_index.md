---
weight: 20
date: "2023-10-24"
author: "Vladimir Lapin"
type: docs
url: /python-net/installation/
feedback: OCRPYNET
title: Installation
description: Adding or updating Aspose.OCR for Python via .NET package in your project.
keywords:
- install
- update
- pip
- PyPI
- package
- download
---

Aspose.OCR for Python via .NET is distributed as a Python Wheel (whl). The package contains all the files necessary for installing and running the library.

## Preparing for installation

1. Before you go any further, make sure you have the [supported version of Python](/ocr/python-net/system-requirements/) and that it is available from the command line. You can check this by running:
   {{< tabs tabID="1" tabTotal="2" tabName1="Windows" tabName2="Unix/macOS" >}}
   {{< tab tabNum="1" >}}
   ```bash
   py --version
   ```
   {{< /tab >}}
   {{< tab tabNum="2" >}}
   ```bash
   python3 --version
   ```
   {{< /tab >}}
   {{< /tabs >}}

   You should get the response like `Python <version number>`. If you do not have Python, or have an unsupported version, install the latest 3.x version from [python.org](https://www.python.org/).

2. Check that the package installer for Python (pip) is available:

   {{< tabs tabID="2" tabTotal="2" tabName1="Windows" tabName2="Unix/macOS" >}}
   {{< tab tabNum="1" >}}
   ```bash
   py -m pip --version
   ```
   {{< /tab >}}
   {{< tab tabNum="2" >}}
   ```bash
   python3 -m pip --version
   ```
   {{< /tab >}}
   {{< /tabs >}}

   If you installed Python with an installer from [python.org](https://www.python.org/) or via [Homebrew](https://brew.sh/), you should already have pip. If you installed Python using your OS package manager, you may have to [install pip separately](https://packaging.python.org/en/latest/guides/installing-using-linux-tools/).

3. Update **pip**, **setuptools**, and **wheel** to the latest versions:

   ```bash
   pip install --upgrade pip setuptools wheel
   ```

## Installing the package

The Aspose.OCR for Python via .NET package can either be installed from [PyPi](https://pypi.org/project/aspose-ocr-python-net/) or downloaded from [releases.aspose.com](https://releases.aspose.com/ocr/python-net/).

### Installing from PyPi

[pip](https://packaging.python.org/en/latest/key_projects/#pip) is the recommended installer. To install the package, run the following command:

```bash
pip install aspose-ocr-python-net
```

In order to use [street photo recognition](/ocr/python-net/recognition/read-text-in-wild/) and [text-in-wild](/ocr/python-net/areas-detection/text-in-wild/) document areas detection method, you must also install the Text-in-wild recognition model, which is distributed as a separate Python package:

```bash
pip install aspose-ocr-models-textinwild-python-net
```

{{% alert color="primary" %}}
You can use Aspose.OCR for Python via .NET without this package, however you will not be able to use the methods and properties that depend on Text-in-wild OCR model.
{{% /alert %}}

### Installing from downloaded package

1. Download Aspose.OCR for Python via .NET package for your platform from [releases.aspose.com](https://releases.aspose.com/ocr/python-net/).
2. Extract the downloaded archive.
3. Install the downloaded package by running **install.sh** or **install.cmd** depending on your platform, or using pip:

   ```bash
   pip install aspose-ocr-python-net.whl
   pip install aspose-ocr-models-textinwild-python-net.whl
   ```

{{% alert color="primary" %}}
You may skip installing **aspose-ocr-models-textinwild-python-net.whl** package if you are not going to use [street photo recognition](/ocr/python-net/recognition/read-text-in-wild/) and [text-in-wild](/ocr/python-net/areas-detection/text-in-wild/) document areas detection method.
{{% /alert %}}

## Updating

The update procedure depends on how you originally installed the Aspose.OCR for Python via .NET package.

{{% alert color="primary" %}}
Refer to [Aspose.OCR for Python via .NET Release Notes](/ocr/python-net/release-notes/) to check if the update might alter the application behavior or require changes to existing code.
{{% /alert %}}

### Getting an update from PyPi

To update the package, run the following command:

```bash
pip install --upgrade aspose-ocr-python-net
```

### Updating with downloaded file

1. Download the new version of Aspose.OCR for Python via .NET package for your platform from [releases.aspose.com](https://releases.aspose.com/ocr/python-net/).
2. Update your current package version to the one you downloaded with pip:

   ```bash
   pip install --upgrade <path to the downloaded Wheel file (.whl)>
   ```
