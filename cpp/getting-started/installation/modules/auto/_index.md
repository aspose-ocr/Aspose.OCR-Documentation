---
weight: 20
date: "2024-04-19"
author: "Vladimir Lapin"
type: docs
url: /cpp/modules/auto/
feedback: OCRCPP
title: Automatically download required resources
description: How to use Aspose.OCR for .NET resources in offline mode.
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

Aspose.OCR for .NET can automatically fetch the necessary resources as needed when you call the method that depends on them. This mode is turned off by default. Check [Important considerations](#important-considerations) before deciding to enable this mode.

1. Create a directory to which resources will be downloaded.
2. Specify the path to that directory in `resource_root_path` property of `AsposeOCRResourceLoadSettings` structure.
3. Set `lazy_load` property of `AsposeOCRResourceLoadSettings` structure to `true`.
4. Apply the resource load settings (`AsposeOCRResourceLoadSettings` structure) using `asposeocr_set_resource_load_settings()` method before calling any other Aspose.OCR method.

```cpp
AsposeOCRResourceLoadSettings load_settings;
std::string root_path = "path/to/files";
load_settings.resource_root_path = root_path.c_str();
load_settings.lazy_load = true;
asposeocr_set_resource_load_settings(load_settings);
```

You also have a flexibility to combine online and offline modes. For example, [provide](/ocr/cpp/modules/management/) the most used resources with your app and allow the app to automatically download rarely used resources in the runtime.

## Important considerations

If you choose to automatically download resources on demand, consider the following:

- The device hosting your application must have access to Internet.
- The application must be allowed outbound HTTP access to the [resource repository's URL](https://github.com/aspose-ocr/resources) in the firewall.
- Depending on your Internet connection's speed, the automatic download of resources may take some time. This will result in increased processing time when you first call a method that depends on the downloaded resource.

If the above-mentioned constraints are not feasible, consider using [manual resource management](/ocr/cpp/modules/management/).
