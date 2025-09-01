---
weight: 20
date: "2024-05-16"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python-cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-cpp/modules/auto/
title: Automatically download required resources
description: How to use Aspose.OCR for Python via C++ resources in offline mode.
keywords:
- install
- update
- repository
- package
- advanced
- models
- extensions
- offline
---

Aspose.OCR for Python via C++ can automatically fetch the necessary resources as needed when you call the method that depends on them. This mode is turned off by default. Check [Important considerations](#important-considerations) before deciding to enable this mode.

1. Create a directory to which resources will be downloaded.
2. Specify the path to that directory in `root_load_path` property of `asposeocr.LoadSettings` object.
3. Set `lazy_load` property of `asposeocr.LoadSettings` object to `true`.
4. Apply the resource loading settings using `asposeocr.set_load_settings()` method before calling any other Aspose.OCR for Python via C++ method.

```python
import asposeocr

load_settings = asposeocr.LoadSettings()
load_settings.root_load_path = "path/to/dir/with/resources"
load_settings.lazy_load = true
asposeocr.set_load_settings(load_settings)
```

You also have a flexibility to combine online and offline modes. For example, [provide](/ocr/python-cpp/modules/management/) the most used resources with your app and allow the app to automatically download rarely used resources in the runtime.

## Important considerations

If you choose to automatically download resources on demand, consider the following:

- The device hosting your application must have access to Internet.
- The application must be allowed outbound HTTP access to the [resource repository's URL](https://github.com/aspose-ocr/resources) in the firewall.
- Depending on your Internet connection's speed, the automatic download of resources may take some time. This will result in increased processing time when you first call a method that depends on the downloaded resource.

If the above-mentioned constraints are not feasible, consider using [manual resource management](/ocr/python-cpp/modules/management/).
