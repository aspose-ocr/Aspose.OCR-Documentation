---
weight: 30
date: "2023-11-24"
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

You can start using Aspose.OCR for JavaScript via C++ right after the [installation](/ocr/javascript-cpp/installation/). In trial mode (without providing a license) you can recognize texts in any supported [languages](/ocr/javascript-cpp/recognition-languages/) and save recognition results in any of the supported [formats](/ocr/javascript-cpp/supported-file-formats/).

However, the following restrictions apply:

- If the number of characters in a recognized image exceeds 300, only the first **300** characters are recognized.
- If the number of characters in a recognized image is less than 300, the first **60%** of characters are recognized.

Apply a license to remove the restriction.

## Getting a temporary license

A temporary license removes a limitation of the trial version for **30 days**. Use it to start building a fully functional OCR application and make the final decision to [purchase](https://purchase.aspose.com/pricing/ocr/cpp) Aspose.OCR for JavaScript via C++ later.

To request a temporary license, visit ["Get a Temporary License"](https://purchase.aspose.com/temporary-license) page.

## Purchasing a license

Aspose.OCR for JavaScript via C++ is licensed either by the number of developers and locations (sites) where the products will be used (_Developer_ and _Site_ licenses) or by pay-per-use (_Metered_ licenses).

Read [License Types](https://purchase.aspose.com/policies/license-types) for details and [purchase a license](https://purchase.aspose.com/pricing/ocr/cpp) that best suits your needs.

## Applying a license

After purchasing a license or obtaining a temporary license, you will receive a file with _.lic_ extension. If needed, you can rename this file and change its extension.

{{% alert color="primary" %}} 
Do not modify the contents of the license file. Even an extra line break or space will invalidate the license.
{{% /alert %}} 

The license must be applied once **before recognition starts**. You can put the file into a folder or load it in a real time from a file data:

```javascript
var Module = {
	onRuntimeInitialized: function()
	{
		// get the license from input field
		const licenseInput = document.getElementById('license-selector');
		licenseInput.addEventListener('change', handleLicenseUpload);

		function handleLicenseUpload(event)
		{
			// get the file
			const files = event.target.files;
			const licenseFile = files[i];
			// initialize file reader
			const reader = new FileReader();
			reader.onload = function(e) {
				const fileData = new Uint8Array(e.target.result);
				// load license
				Module.AsposeOCRSetLicenseFromData(fileData);
			};
			// read license file
			reader.readAsArrayBuffer(licenseFile);
		}
	}
};
```
