---
weight: 30
date: "2022-06-08"
author: "Vladimir Lapin"
type: docs
url: /net/licensing/
feedback: OCRNET
aliases:
- /net/evaluate-aspose-ocr/
title: Licensing
description: Learn how to obtain and apply Aspose.OCR for .NET license and discover limitations of the trial version.
keywords:
- license
- evaluation
- trial
- free
- purchase
---

Aspose.OCR for .NET is a commercially licensed product that can be used in trial (evaluation) mode.

## Free trial

You can start using Aspose.OCR for .NET right after the [installation](/ocr/net/installation/). In trial mode (without providing a license) you can recognize texts in any supported [languages](/ocr/net/recognition-languages/) and save recognition results in any of the supported [formats](/ocr/net/supported-file-formats/).

However, the following restrictions apply:

- If the number of characters in a recognized image exceeds 300, only the first **300** characters are recognized.
- If the number of characters in a recognized image is less than 300, the first **60%** of characters are recognized.

Apply a license to remove the restriction.

## Getting a temporary license

A temporary license removes a limitation of the trial version for **30 days**. Use it to start building a fully functional OCR application and make the final decision to [purchase](https://purchase.aspose.com/pricing/ocr/net) Aspose.OCR for .NET later.

To request a temporary license, visit ["Get a Temporary License"](https://purchase.aspose.com/temporary-license) page.

## Purchasing a license

Aspose.OCR for .NET is licensed either by the number of developers and locations (sites) where the products will be used (_Developer_ and _Site_ licenses) or by pay-per-use (_Metered_ licenses).

Read [License Types](https://purchase.aspose.com/policies/license-types) for details and [purchase a license](https://purchase.aspose.com/pricing/ocr/net) that best suits your needs.

## Applying a developer or site license

After purchasing a license or obtaining a temporary license, you will receive a file with _.lic_ extension. If needed, you can rename this file and change its extension.

{{% alert color="primary" %}} 
Do not modify the contents of the license file. Even an extra line break or space will invalidate the license.
{{% /alert %}} 

The license must be applied once per application or process lifecycle before recognition starts. For _desktop applications_, it is recommended to load the license in the `Initialize` method of the main form. For _web applications_, load it in the `Session_Start()` method of **global.asax** file.

### Loading a license from file

Put the license file to a folder on your computer and insert the following code in your startup method:

```csharp
// Initialize the licensing object
Aspose.OCR.License license = new Aspose.OCR.License();

// Load the license from file
license.SetLicense("Aspose_OCR_License_File.lic");
```
If only the name of the license file (without path) is specified, `SetLicense` method will look for the license file in the following locations:

- the folder that contains Aspose.OCR for .NET component (_Aspose.OCR.dll_);
- the folder that contains the calling assembly;
- the folder that contains the entry (startup) assembly.

Alternatively, you can store the license file in any folder on your computer and specify an absolute or relative path. If you prefer to load the license from the explicit path, provide the full path in `SetLicense` method.

### Loading a license from stream

Insert the following code in your startup method:

```csharp
// Initialize the licensing object
Aspose.OCR.License license = new Aspose.OCR.License();

// Read the license from file
System.IO.FileStream lisenseStream = new System.IO.FileStream(@"C:\Aspose_OCR_License_File.lic", System.IO.FileMode.Open, System.IO.FileAccess.Read);

// Load the license
license.SetLicense(licenseStream);
```

### Including a license file as an embedded resource

You can include the license file as an embedded resource into one of the assemblies that call Aspose.OCR for .NET. This ensures that the file is not accidentally lost.

- In Microsoft Visual Studio, right-click the project in **Solution Explorer** and select **Add | Existing Item...** from the context menu.
- Select the license (_.lic_) file and click **Add** button.
- Select the license file in **Solution Explorer** and set its **Build Action** property to _Embedded resource_.

Then insert the following code in your startup method:

```c#
// Initialize the licensing object
Aspose.OCR.License license = new Aspose.OCR.License();

// Load the license from file
license.SetLicense("Aspose_OCR_License_File.lic");
```

You do not need to call `GetExecutingAssembly` and `GetManifestResourceStream` methods of the `System.Reflection.Assembly` class to access the embedded license. `Aspose.OCR.License` class will automatically find the license file in the embedded resources.

## Applying a metered license

When you purchase a metered license, you will receive a Public/Private Key pair instead of a license file. Use the following code in your startup method to apply the license keys:

```csharp
// License key pair
string publicKey = "PUBLIC-LICENSE-KEY";
string privateKey = "PRIVATE-LICENSE-KEY";

// Initialize the metered license
Aspose.OCR.Metered meteredLicense = new Aspose.OCR.Metered();
meteredLicense.SetMeteredKey(publicKey, privateKey);
```

Your usage will be recorded locally and regularly reported back to Aspose servers. You will be billed monthly for what you use. This licensing mechanism requires that the computer running the OCR application has a stable Internet connection and that the application is not blocked by a firewall.

Read [Metered Licensing FAQ](https://purchase.aspose.com/faqs/licensing/metered) for in-depth technical and business details.

## Licensing multiple Aspose products

Even if you have a single license for all Aspose products (such as [Aspose.Total for .NET](https://products.aspose.com/total/net/)), you still need to apply the license separately to **each** Aspose product you are using in your application.

Every Aspose product has a `License` class in its namespace. Use the fully qualified `License` class name when applying licenses to each product to avoid ambiguity. For example:  
  
  ```c#
  // Aspose.OCR
  Aspose.OCR.License OCRLicense = new Aspose.OCR.License();
  OCRLicense.SetLicense("Aspose_OCR_License_File.lic");

  // Aspose.BarCode
  Aspose.BarCode.License barcodeLicense = new Aspose.BarCode.License();
  barcodeLicense.SetLicense("Aspose_BarCode_License_File.lic");
  ```
