---
weight: 20
date: "2024-12-18"
author: "Vladimir Lapin"
type: docs
url: /net/characters-whitelist/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
aliases:
- /net/provide-allowed-characters-during-ocr-operation/
title: Defining the whitelist of characters
description: How to limit the set of characters Aspose.OCR engine will look for.
keywords:
- whitelist
- symbols
- characters
- letters
- allow
---

Limiting a subset of characters instead of using the [full set](/ocr/net/recognition-languages/) can greatly improve recognition accuracy, increase speed, and reduce resource consumption. A list of characters can be automatically [identified](/ocr/net/characters-identify/) from an image using the built-in Aspose.OCR mechanisms.

You can specify a list of characters Aspose.OCR engine will look for in `AllowedSymbols` property of [recognition settings](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/). The characters are provided as a _case-sensitive_ string.

Characters that do not match the provided list are ignored.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Limit a subset of recognized characters
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.AllowedSymbols = "AÁBCDEÉFG12345";
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
