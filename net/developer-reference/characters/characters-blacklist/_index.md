---
weight: 30
date: "2023-11-30"
author: "Vladimir Lapin"
type: docs
url: /net/characters-blacklist/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
aliases:
- /net/provide-ignored-characters-during-ocr-operation/
title: Defining the blacklist of characters
description: How to ignore certain image defects that may be incorrectly recognized as characters.
keywords:
- blacklist
- symbols
- characters
- letters
- deny
---

Image defects such as dirt and scratches may cause recognition errors. For example, dots or other print defects next to letters can be incorrectly recognized as punctuation or diacritical marks.

To ignore certain characters during recognition, provide them in `IgnoredSymbols` property of [recognition settings](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/) as a case-sensitive string:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Limit a subset of recognized characters
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.IgnoredSymbols = "Áá";
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
