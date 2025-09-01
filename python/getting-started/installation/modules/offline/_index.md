---
weight: 20
date: "2024-05-30"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/modules/offline/
feedback: OCRPYNET
title: Using offline resources
description: How to use Aspose.OCR for Python via .NET resources in offline mode.
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

While Aspose.OCR for Python via .NET can automatically fetch the necessary resources as needed, there are certain scenarios where manual downloading of these resources and providing them with your application could be beneficial:

- Your application needs to work in an environment where Internet access is limited or unavailable.
- You (or the application user) do not have the ability to change firewall rules.
- You want to reduce startup time and improve overall performance, particularly for applications requiring fast response times.
- All application files must pass the strict audit and cannot be changed/added in the runtime.

To make the application work in the offline mode:

1. Create a folder in the application's working directory.
2. Download the required resource files from the Aspose.OCR [resource repository](https://github.com/aspose-ocr/resources) to the folder. To find more information on a specific resource, refer to the following [link](https://github.com/aspose-ocr/resources/blob/main/README.md#resources).
3. Provide the absolute or relative path to the folder using `Resources.set_local_path()` method. For example: `Resources.set_local_path("aspose/ocr", false);`.
4. Block automatic downloading of resources by calling `Resources.allow_automatic_downloads(false)`.
5. Do not forget to include a directory with downloaded resources in your distributive, otherwise the related functionality will fail.

You also have a flexibility to combine online and offline modes. For example, provide the most used resources with your app and download rarely used resources in the runtime.

## Example

```python
Resources.set_local_path("aspose/ocr")
Resources.allow_automatic_downloads(false);
# Set recognition language
recognitionSettings = RecognitionSettings()
recognitionSettings.language = Language.UKR
```
