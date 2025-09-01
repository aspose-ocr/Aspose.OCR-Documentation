---
weight: 10
date: "2022-10-21"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /cpp/installation/gpu/
feedback: OCRCPP
title: Installing GPU-accelearated package
description: Adding GPU-accelerated package of Aspose.OCR for C++ to your project.
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
2. [Install](https://docs.nvidia.com/cuda/index.html#installation-guides) the CUDA Toolkit.
3. Install the NVIDIA CUDA Deep Neural Network library (cuDNN):
    1. [Download](https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html) cuDNN.
    2. Extract the downloaded cuDNN archive to your system.
    3. Add the path to the `bin` subfolder of the folder where cuDNN was extracted to the system PATH variable.
4. Copy all files from `bin` subfolder of the folder where cuDNN was extracted to `bin` folder of the project.
