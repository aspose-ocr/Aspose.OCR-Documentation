---
weight: 10
date: "2024-04-19"
author: "Vladimir Lapin"
type: docs
url: /cpp/modules/management/
feedback: OCRCPP
title: Managing downloadable resources
description: How to manage Aspose.OCR for C++ downloadable modules.
keywords:
- install
- update
- repository
- package
- advanced
- models
- extensions
- online
---

To add OCR modules to your project:

1. Download the required resources from the Aspose.OCR [resource repository](https://github.com/aspose-ocr/resources) to some directory on your computer.
2. Specify the path to that directory in `resource_root_path` property of `AsposeOCRResourceLoadSettings` structure.
3. Apply the resource load settings (`AsposeOCRResourceLoadSettings` structure) using `asposeocr_set_resource_load_settings()` method before calling any other Aspose.OCR method.

```cpp
AsposeOCRResourceLoadSettings load_settings;
std::string root_path = "path/to/files";
load_settings.resource_root_path = root_path.c_str();
asposeocr_set_resource_load_settings(load_settings);
```

{{% alert color="primary" %}}
Do not forget to include a directory with downloaded resources in your distributive, otherwise the related functionality will fail.
{{% /alert %}}
