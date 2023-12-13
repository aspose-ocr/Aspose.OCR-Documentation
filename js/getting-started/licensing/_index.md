---
weight: 30
date: "2023-12-07"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/licensing/
title: Licensing
description: Learn how to obtain and apply Aspose.OCR for JavaScript via C++ license and discover limitations of the trial version.
keywords:
- license
- evaluation
- trial
- free
- purchase
---

Aspose.OCR for JavaScript via C++ is a commercially licensed product that can be used in trial (evaluation) mode.

## Free trial

You can start using Aspose.OCR for JavaScript via C++ right after the [installation](/ocr/javascript-cpp/installation/). In evaluation mode (without providing a license) you can recognize texts in any supported [languages](/ocr/javascript-cpp/recognition-languages/) and save recognition results in any of the supported [formats](/ocr/javascript-cpp/supported-file-formats/).

However, if you do not provide the license, only the first **300** characters from the image are recognized.

Apply a license to remove the restriction.

## Getting a temporary license

A temporary license removes a limitation of the trial version for **30 days**. Use it to start building a fully functional OCR application and make the final decision to [purchase](https://purchase.aspose.com/admin/pricing/ocr/javascript-cpp) Aspose.OCR for JavaScript via C++ later.

To request a temporary license, visit ["Get a Temporary License"](https://purchase.aspose.com/temporary-license) page.

## Purchasing a license

Aspose.OCR for JavaScript via C++ is licensed by the number of developers and locations (sites) where the products will be used (_Developer_ and _Site_ licenses).

Read [License Types](https://purchase.aspose.com/policies/license-types) for details and [purchase a license](https://purchase.aspose.com/admin/pricing/ocr/javascript-cpp) that best suits your needs.

## Applying a license

After purchasing a license or obtaining a temporary license, you will receive a file with _.lic_ extension. If needed, you can rename this file and change its extension.

{{% alert color="primary" %}} 
Do not modify the contents of the license file. Even an extra line break or space will invalidate the license.
{{% /alert %}} 

The license must be applied only once, **before recognition starts**. You can load the license from a file, Base64 encoded string, or request a user to provide it.

Method | Usage
------ | -----
`Module.AsposeOCRSetLicenseFromData()` | Load a license from an array of bytes (`ArrayBuffer` object).
`Module.AsposeOCRGetState()` | Checks the current licensing status:<ul><li>`true` - licensed</li><li>`false` - unlicensed</li></ul>

### Examples

{{< tabs tabID="1" tabTotal="3" tabName1="Load license from file" tabName2="Load license from Base64 code" tabName3="Get license from user" >}}
{{< tab tabNum="1" >}}
```javascript
var Module = {
	onRuntimeInitialized: function()
	{
		// Place the license file in the same directory as a web page
		fetch("./Aspose.OCR.lic").then(bytes => bytes.arrayBuffer()).then(licenseData => {
			// Load license
			Module.AsposeOCRSetLicenseFromData(licenseData);
			// Check license status
			if(Module.AsposeOCRGetState()) console.log("Licensed");
			else console.log("Unlicensed");
		});
	}
};
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```javascript
var Module = {
	onRuntimeInitialized: function()
	{
		// Base64 encoded license file
		const license = "data:application/octet-stream;base64,PD94bWwgdm...TGljZW5zZT4=";
		fetch(license).then(bytes => bytes.arrayBuffer()).then(licenseData => {
			// Load license
			Module.AsposeOCRSetLicenseFromData(licenseData);
			// Check license status
			if(Module.AsposeOCRGetState()) console.log("Licensed");
			else console.log("Unlicensed");
		});
	}
};
```
{{< /tab >}}
{{< tab tabNum="3" >}}
```javascript
var Module = {
	onRuntimeInitialized: function()
	{
		// Get the license from input field
		const licenseInput = document.getElementById("license-file");
		licenseInput.addEventListener("change", applyLicense);

		function applyLicense(event)
		{
			// Read the license file contents
			const files = event.target.files;
			const licenseFile = files[0];
			const reader = new FileReader();
			reader.readAsArrayBuffer(licenseFile);
			// Apply the license
			reader.onload = function(e) {
				const fileData = new Uint8Array(e.target.result);
				// Load license
				Module.AsposeOCRSetLicenseFromData(fileData);
				// Check license status
				if(Module.AsposeOCRGetState()) console.log("Licensed");
				else console.log("Unlicensed");
			};
		}
	}
};
```
{{< /tab >}}
{{< /tabs >}}
