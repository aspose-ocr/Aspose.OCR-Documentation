---
weight: 10
date: "2022-10-21"
author: "Vladimir Lapin"
type: docs
url: /net/installation/gpu/
feedback: OCRNET
title: Installing GPU-accelearated package
description: Adding GPU-accelerated package of Aspose.OCR for .NET to your project.
keywords:
- install
- update
- GPU
- CUDA
- package
- zip
- MSI
- download
---

GPU-accelerated OCR engine requires a [CUDA capable GPU] and [NVIDIA CUDA Toolkit](https://developer.nvidia.com/cuda-downloads). To use the package, make sure your system meets the following prerequisites:

1. Check whether your GPU [supports](https://developer.nvidia.com/cuda-gpus) NVIDIA® CUDA®.
2. [Install](https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/index.html) the CUDA Toolkit.
3. Install the NVIDIA CUDA Deep Neural Network library (cuDNN):
    1. [Download](https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html) cuDNN.
    2. Extract the downloaded cuDNN archive to your system.
    3. Add the path to the `bin` subfolder of the folder where cuDNN was extracted to the system PATH variable.
4. Copy all files from the `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.х` to `bin` folder of the project.

## Compatibility

Aspose.OCR for .NET version | CUDA Toolkit version
--------------------------- | --------------------
22.10 and above             | 11.4 and above
Older versions              | 11.0.3 and above
