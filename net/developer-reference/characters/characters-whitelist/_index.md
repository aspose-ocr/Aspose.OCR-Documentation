---
weight: 20
date: "2023-11-30"
author: "Vladimir Lapin"
type: docs
url: /net/characters-whitelist/
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
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
