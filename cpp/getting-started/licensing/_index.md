---
weight: 30
date: "2022-12-07"
author: "Vladimir Lapin"
type: docs
url: /cpp/licensing/
feedback: OCRCPP
title: Licensing
description: Learn how to obtain and apply Aspose.OCR for C++ license and discover limitations of the trial version.
keywords:
- license
- evaluation
- trial
- free
- purchase
---

Aspose.OCR for C++ is a commercially licensed product that can be used in trial (evaluation) mode.

## Free trial

You can start using Aspose.OCR for C++ right after the [installation](/ocr/cpp/installation/). In trial mode (without providing a license) you can recognize texts in any supported [languages](/ocr/cpp/recognition-languages/) and save recognition results in any of the supported [formats](/ocr/cpp/supported-file-formats/).

However, the following restrictions apply:

- If the number of characters in a recognized image exceeds 300, only the first **300** characters are recognized.
- If the number of characters in a recognized image is less than 300, the first **60%** of characters are recognized.

Apply a license to remove the restriction.

## Getting a temporary license

A temporary license removes a limitation of the trial version for **30 days**. Use it to start building a fully functional OCR application and make the final decision to [purchase](https://purchase.aspose.com/pricing/ocr/cpp) Aspose.OCR for C++ later.

To request a temporary license, visit ["Get a Temporary License"](https://purchase.aspose.com/temporary-license) page.

## Purchasing a license

Aspose.OCR for C++ is licensed either by the number of developers and locations (sites) where the products will be used (_Developer_ and _Site_ licenses) or by pay-per-use (_Metered_ licenses).

Read [License Types](https://purchase.aspose.com/policies/license-types) for details and [purchase a license](https://purchase.aspose.com/pricing/ocr/cpp) that best suits your needs.

## Applying a developer or site license

After purchasing a license or obtaining a temporary license, you will receive a file with _.lic_ extension. If needed, you can rename this file and change its extension.

{{% alert color="primary" %}} 
Do not modify the contents of the license file. Even an extra line break or space will invalidate the license.
{{% /alert %}} 

The license must be applied once per application or process lifecycle before recognition starts. For _desktop applications_, it is recommended to load the license in the `Initialize` function of the main form. For _web applications_, load it in the `Session_Start()` function of **global.asax** file.

### Loading a license from file

Put the license file to a folder on your computer and insert the following code in your startup function:

```cpp
const std::string lic = "Aspose_OCR_License_File.lic";
aspose::ocr::set_license(lic.c_str());
```
If only the name of the license file (without path) is specified, `set_license` function will look for the license file in the following locations:

- the folder that contains Aspose.OCR for C++ component (_Aspose.OCR.dll_);
- the folder that contains the application's executable file.

Alternatively, you can store the license file in any folder on your computer and specify an absolute or relative path. If you prefer to load the license from the explicit path, provide the full path in `set_license` function.

### Checking the license state

To validate whether the license is valid, use the following code:

```cpp
std::wcout << aspose::ocr::get_state() << '\n';
```

This code will return `true` if the license is set and valid and `false` if there is a problem with the license.

## Licensing multiple Aspose products

Even if you have a single license for all Aspose products (such as [Aspose.Total for C++](https://products.aspose.com/total/cpp/)), you still need to apply the license separately to **each** Aspose product you are using in your application.
