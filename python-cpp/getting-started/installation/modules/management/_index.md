---
weight: 10
date: "2024-05-16"
author: "Vladimir Lapin"
type: docs
url: /python-cpp/modules/management/
title: Managing downloadable resources
description: How to manage Aspose.OCR for Python via C++ downloadable modules.
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
2. Specify the path to that directory in `root_load_path` property of `asposeocr.LoadSettings` object.
3. Apply the resource loading settings using `asposeocr.set_load_settings()` method before calling any other Aspose.OCR for Python via C++ method.

```python
import asposeocr

load_settings = asposeocr.LoadSettings()
load_settings.root_load_path = "extra/resources"
asposeocr.set_load_settings(load_settings)
```

{{% alert color="primary" %}}
Do not forget to include a directory with downloaded resources when moving the project between different systems, otherwise the related functionality will fail.
{{% /alert %}}
