---
weight: 30
date: "2023-12-11"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_nodejs-cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /nodejs-cpp/licensing/
title: Licensing
description: Learn how to obtain and apply Aspose.OCR for Node.js via C++ license and discover limitations of the trial version.
keywords:
- license
- evaluation
- trial
- free
- purchase
---

Aspose.OCR for Node.js via C++ is a commercially licensed product that can be used in trial (evaluation) mode.

## Free trial

You can start using Aspose.OCR for Node.js via C++ right after the [installation](/ocr/nodejs-cpp/installation/). In evaluation mode (without providing a license) you can recognize texts in any supported [languages](/ocr/nodejs-cpp/recognition-languages/) and save recognition results in any of the supported [formats](/ocr/nodejs-cpp/supported-file-formats/).

However, if you do not provide the license, only the first **300** characters from the image are recognized.

Apply a license to remove the restriction.

## Getting a temporary license

A temporary license removes a limitation of the trial version for **30 days**. Use it to start building a fully functional OCR application and make the final decision to [purchase](https://purchase.aspose.com/admin/pricing/ocr/family) Aspose.OCR for Node.js via C++ later.

To request a temporary license, visit ["Get a Temporary License"](https://purchase.aspose.com/temporary-license) page.

## Purchasing a license

Aspose.OCR for Node.js via C++ is licensed by the number of developers and locations (sites) where the products will be used (_Developer_ and _Site_ licenses).

Read [License Types](https://purchase.aspose.com/policies/license-types) for details and [purchase a license](https://purchase.aspose.com/admin/pricing/ocr/family) that best suits your needs.

## Applying a license

After purchasing a license or obtaining a temporary license, you will receive a file with _.lic_ extension. If needed, you can rename this file and change its extension.

{{% alert color="primary" %}} 
Do not modify the contents of the license file. Even an extra line break or space will invalidate the license.
{{% /alert %}} 

The license must be applied only once, **before recognition starts**.

Method | Usage
------ | -----
`AsposeOCRSetLicenseFromData()` | Load a license from an array of bytes.
`AsposeOCRGetState()` | Checks the current licensing status:<ul><li>`true` - licensed</li><li>`false` - unlicensed</li></ul>

### Examples

```js
const Module = require("./asposeocr");
const fs = require("fs");

Module.onRuntimeInitialized = async _ => {
	// Place the license file in the project directory
	fs.readFile("Aspose.OCR.lic", (err, licenseData) => {
		const licenseBytes = new Uint8Array(licenseData);
		Module.AsposeOCRSetLicenseFromData(licenseBytes);
		// Verify licensing status
		if(Module.AsposeOCRGetState()) console.log("Licensed");
		else console.log("Unlicensed");
	});
}
```
