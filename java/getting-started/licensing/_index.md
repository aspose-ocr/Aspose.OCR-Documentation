---
weight: 50
date: "2022-06-10"
author: "Vladimir Lapin"
type: docs
url: /java/licensing/
title: Licensing
description: Learn how to obtain and apply Aspose.OCR for Java license and discover limitations of the trial version.
keywords:
- license
- evaluation
- trial
- free
- purchase
- Java
---

Aspose.OCR for Java is a commercially licensed product that can be used in trial (evaluation) mode.

## Free trial

You can start using Aspose.OCR for Java right after the [installation](/ocr/net/installation/). In trial mode (without providing a license) you can recognize texts in any supported [languages](/ocr/java/recognition-languages/) and save recognition results in any of the supported [formats](/ocr/java/supported-file-formats/).

However, the following restrictions apply:

- If the number of characters in a recognized image exceeds 300, only the first **300** characters are recognized.
- If the number of characters in a recognized image is less than 300, the first **60%** of characters are recognized.

Apply a license to remove the restriction.

## Getting a temporary license

A temporary license removes a limitation of the trial version for **30 days**. Use it to start building a fully functional OCR application and make the final decision to [purchase](https://purchase.aspose.com/pricing/ocr/java) Aspose.OCR for Java later.

To request a temporary license, visit ["Get a Temporary License"](https://purchase.aspose.com/temporary-license) page.

## Purchasing a license

Aspose.OCR for .NET is licensed either by the number of developers and locations (sites) where the products will be used (_Developer_ and _Site_ licenses) or by pay-per-use (_Metered_ licenses).

Read [License Types](https://purchase.aspose.com/policies/license-types) for details and [purchase a license](https://purchase.aspose.com/pricing/ocr/java) that best suits your needs.

## Applying a license

After purchasing a license or obtaining a temporary license, you will receive a file with _.lic_ extension. If needed, you can rename this file and change its extension.

{{% alert color="primary" %}} 
Do not modify the contents of the license file. Even an extra line break or space will invalidate the license.
{{% /alert %}} 

The license must be applied once per application or process lifecycle before recognition starts.

### Loading a license from file

Put the license file to a folder on your computer and insert the following code before calling recognition methods:

```java
// Initialize the licensing component
com.aspose.ocr.License license = new com.aspose.ocr.License();

// Load the license from file
license.SetLicense("Aspose_OCR_License_File.lic");
```
If only the name of the license file (without path) is specified, `SetLicense` method will look for the license file in the folder that contains _Aspose.OCR.jar_ and in the folder that contain JAR files of your application.

### Loading a license from stream

Insert the following code before calling recognition methods:

```java
// Initialize the licensing object
com.aspose.ocr.License license = new com.aspose.ocr.License();

// Load the license form stream
license.setLicense(new java.io.FileInputStream("Aspose_OCR_License_File.lic"));
```

## Validating the license

You can check if the license is valid and has been properly applied. Check the return value of `isValid` method of the [`License`](https://reference.aspose.com/ocr/java/com.aspose.ocr/license) class - if the license is valid and is properly applied, this method will return `true`.

```java
// Initialize the licensing component
com.aspose.ocr.License license = new com.aspose.ocr.License();

// Load the license from file
license.SetLicense("Aspose_OCR_License_File.lic");

// Validate the license
if (License.isValid()) {
    System.out.println("License is valid!");
}
```
