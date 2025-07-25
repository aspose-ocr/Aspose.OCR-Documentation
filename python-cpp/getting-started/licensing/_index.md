---
weight: 30
date: "2024-05-16"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python-cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-cpp/licensing/
title: Licensing
description: Learn how to obtain and apply Aspose.OCR for Python via C++ license and discover limitations of the trial version.
keywords:
- license
- evaluation
- trial
- free
- purchase
---

Aspose.OCR for Python via C++ is a commercially licensed product that can be used in trial (evaluation) mode.

## Free trial

You can start using Aspose.OCR for Python via C++ right after the [installation](/ocr/python-cpp/installation/). In trial mode (without providing a license) you can recognize texts in any supported [languages](/ocr/python-cpp/recognition-languages/) and save recognition results in any of the supported [formats](/ocr/python-cpp/supported-file-formats/).

However, the following restrictions apply:

- If the number of characters in a recognized image exceeds 300, only the first **300** characters are recognized.
- If the number of characters in a recognized image is less than 300, the first **60%** of characters are recognized.

Apply a license to remove the restriction.

## Getting a temporary license

A temporary license removes a limitation of the trial version for **30 days**. Use it to start building a fully functional OCR application and make the final decision to [purchase](https://purchase.aspose.com/admin/pricing/ocr/family) Aspose.OCR for Python via C++ later.

To request a temporary license, visit ["Get a Temporary License"](https://purchase.aspose.com/temporary-license) page.

## Purchasing a license

Aspose.OCR for Python via C++ is licensed by the number of developers and locations (sites) where the products will be used (_Developer_ and _Site_ licenses).

Read [License Types](https://purchase.aspose.com/policies/license-types) for details and [purchase a license](https://purchase.aspose.com/admin/pricing/ocr/family) that best suits your needs.

## Applying a developer or site license

After purchasing a license or obtaining a temporary license, you will receive a file with _.lic_ extension. If needed, you can rename this file and change its extension.

{{% alert color="primary" %}} 
Do not modify the contents of the license file. Even an extra line break or space will invalidate the license.
{{% /alert %}} 

The license must be applied once per application or process lifecycle before recognition starts.

```python
import asposeocr
# Load the license from file
asposeocr.set_license("Aspose-OCR-Python-via-CPP.lic")
```

If only the name of the license file (without path) is specified, `set_license()` method will look for the license file in the script's working directory.

Alternatively, you can store the license file in any directory on your computer and specify an absolute path in `set_license()` method.

## Licensing multiple Aspose products

Even if you have a single license for several Aspose products, you still need to apply the license separately to each Aspose module you are using in your script.
