---
weight: 30
date: "2022-09-16"
author: "Vladimir Lapin"
type: docs
url: /java/licensing/
aliases:
- /java/evaluate-aspose-ocr/
title: Licensing
description: Learn how to obtain and apply Aspose.OCR for Java license and discover limitations of the trial version.
keywords:
- license
- evaluation
- trial
- free
- purchase
---

Aspose.OCR for Java is a commercially licensed product that can be used in trial (evaluation) mode.

## Free trial

You can start using Aspose.OCR for Java right after the [installation](/ocr/java/installation/). In trial mode (without providing a license) you can recognize texts in any supported [languages](/ocr/java/recognition-languages/) and save recognition results in any of the supported [formats](/ocr/java/supported-file-formats/).

However, the following restrictions apply:

- If the number of characters in a recognized image exceeds 300, only the first **300** characters are recognized.
- If the number of characters in a recognized image is less than 300, the first **60%** of characters are recognized.

Apply a license to remove the restriction.

## Getting a temporary license

A temporary license removes a limitation of the trial version for **30 days**. Use it to start building a fully functional OCR application and make the final decision to [purchase](https://purchase.aspose.com/admin/pricing/ocr/java) Aspose.OCR for Java later.

To request a temporary license, visit ["Get a Temporary License"](https://purchase.aspose.com/temporary-license) page.

## Purchasing a license

Aspose.OCR for Java is licensed either by the number of developers and locations (sites) where the products will be used (_Developer_ and _Site_ licenses) or by pay-per-use (_Metered_ licenses).

Read [License Types](https://purchase.aspose.com/policies/license-types) for details and [purchase a license](https://purchase.aspose.com/admin/pricing/ocr/java) that best suits your needs.

## Applying a developer or site license

After purchasing a license or obtaining a temporary license, you will receive a file with _.lic_ extension. If needed, you can rename this file and change its extension.

{{% alert color="primary" %}} 
Do not modify the contents of the license file. Even an extra line break or space will invalidate the license.
{{% /alert %}} 

The license must be applied once per application or process lifecycle before recognition starts.

### Loading a license from file

Put the license file to a folder on your computer and insert the following code in your startup method:

```java
// Initialize the licensing component
com.aspose.ocr.License license = new com.aspose.ocr.License();

// Load the license from file
license.SetLicense("Aspose_OCR_License_File.lic");
```
If only the name of the license file (without path) is specified, `SetLicense` method will look for the license file in the following locations:

- the folder that contains Aspose.OCR.jar;
- the folder that contain JAR files of your application.

Alternatively, you can store the license file in any folder on your computer and specify an absolute or relative path. If you prefer to load the license from the explicit path, provide the full path in `SetLicense` method.

### Loading a license from stream

Insert the following code in your startup method:

```java
// Initialize the licensing component
com.aspose.ocr.License license = new com.aspose.ocr.License();

// Load the license from stream
license.setLicense(new java.io.FileInputStream("Aspose_OCR_License_File.lic"));
```

## Applying a metered license

When you purchase a metered license, you will receive a Public/Private Key pair instead of a license file. Use the following code in your startup method to apply the license keys:

```java
// License key pair
String publicKey = "PUBLIC-LICENSE-KEY";
String privateKey = "PRIVATE-LICENSE-KEY";

// Initialize the metered license
Metered meteredLicense = new com.aspose.ocr.metered.Metered();
meteredLicense.setMeteredKey(publicKey, privateKey);
```

Your usage will be recorded locally and regularly reported back to Aspose servers. You will be billed monthly for what you use. This licensing mechanism requires that the computer running the OCR application has a stable Internet connection and that the application is not blocked by a firewall.

Read [Metered Licensing FAQ](https://purchase.aspose.com/faqs/licensing/metered) for in-depth technical and business details.

## Validating the license

To check the current state of the time limited (file-based) license:

```java
// Initialize the licensing component
com.aspose.ocr.License license = new com.aspose.ocr.License();

// Load the license from file
license.SetLicense("Aspose_OCR_License_File.lic");

// Validate the license
if(License.isValid()) {
    System.out.println("The license is valid!");
} else {
    System.out.println("The license is invalid!");
}
```

To check the metered license usage:

```java
// License key pair
String publicKey = "PUBLIC-LICENSE-KEY";
String privateKey = "PRIVATE-LICENSE-KEY";

// Initialize the metered license
Metered meteredLicense = new com.aspose.ocr.metered.Metered();
meteredLicense.setMeteredKey(publicKey, privateKey);

// Remaining license limit
double remainingCalls = meteredLicense.getConsumptionCredit() - meteredLicense.getConsumptionQuantity();
```

## Licensing multiple Aspose products

Even if you have a single license for all Aspose products (such as [Aspose.Total for Java](https://products.aspose.com/total/java/)), you still need to apply the license separately to **each** Aspose product you are using in your application.

Every Aspose product has a `License` class in its namespace. Use the fully qualified `License` class name when applying licenses to each product to avoid ambiguity. For example:  
  
```java
// Aspose.OCR
com.aspose.ocr.License ocrLicense = new com.aspose.ocr.License();
ocrLicense.SetLicense("Aspose_OCR_License_File.lic");

// Aspose.BarCode
com.aspose.barcode.License barcodeLicense = new com.aspose.barcode.License();
barcodeLicense.SetLicense("Aspose_BarCode_License_File.lic");
```
