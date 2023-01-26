---
weight: 100
date: "2023-01-17"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/passport/
feedback: OCRNET
title: Extracting text from passport images
description: How to digitize scanned or photographed passports by automatically extracting text from them.
keywords:
- read
- extract
- OCR
- recognize
- check
- image
- photo
- passport
---

Automatic passport recognition and verification is a very common task in many areas: border control, banking, security, and so on. However, manually re-typing text is an error-prone and time-consuming process, and mistakes can lead to security breaches and other undesirable consequences.

Aspose.OCR offers a special recognition algorithm that extracts text from scanned or photographed passports, which can then be automatically saved to the database or automatically verified.

To extract text from a passport image, use [`RecognizePassport`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizepassport/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-passport/).

The method returns a [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object containing the passport data.

{{< tabs tabID="1" tabTotal="2" tabName1="Read passport from path" tabName2="Read passport from memory" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.PassportRecognitionSettings recognitionSettings = new Aspose.OCR.PassportRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizePassport("passport.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.PassportRecognitionSettings recognitionSettings = new Aspose.OCR.PassportRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
using(MemoryStream ms = new MemoryStream())
{
	using(FileStream fs = new FileStream("passport.png", FileMode.Open, FileAccess.Read))
	{
		fs.CopyTo(ms);
		Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizePassport(ms, recognitionSettings);
		Console.WriteLine(result.RecognitionText);
	}
}
```
{{< /tab >}}
{{< /tabs >}}
