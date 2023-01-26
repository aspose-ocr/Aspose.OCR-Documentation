---
weight: 30
date: "2022-08-22"
author: "Vladimir Lapin"
type: docs
url: /net/characters-blacklist/
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

To ignore certain characters during recognition, provide them in [`IgnoredCharacters`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/ignoredcharacters/) property of [recognition settings](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/) as a case-sensitive string:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.IgnoredCharacters = "Áá";
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
