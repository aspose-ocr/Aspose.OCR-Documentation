---
weight: 90
date: "2023-01-17"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/id-card/
feedback: OCRNET
title: Extracting text from ID cards
description: How to digitize scanned or photographed ID cards by automatically extracting text from them.
keywords:
- read
- extract
- OCR
- recognize
- check
- image
- photo
- ID
- card
---

An identity card (commonly abbreviated as _ID_) is a small plastic or paper card that is used to verify a person's identity. This can be an identity card, work permit, residence permit, passport card or other identity document. Manually re-typing text from ID cards, especially in batch mode, is time consuming and commonly leads to errors.

Aspose.OCR offers a special recognition algorithm that extracts text from scanned or photographed ID cards, which can then be automatically saved to the database or automatically verified.

To extract text from an ID card, use [`RecognizeIDCard`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizeidcard/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-id-card/).

The method returns a [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object containing the identity data.

{{< tabs tabID="1" tabTotal="2" tabName1="Read ID card from path" tabName2="Read ID card from memory" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.IDCardRecognitionSettings recognitionSettings = new Aspose.OCR.IDCardRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeIDCard("id-card.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.IDCardRecognitionSettings recognitionSettings = new Aspose.OCR.IDCardRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
using(MemoryStream ms = new MemoryStream())
{
	using(FileStream fs = new FileStream("id-card.png", FileMode.Open, FileAccess.Read))
	{
		fs.CopyTo(ms);
		Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeIDCard(ms, recognitionSettings);
		Console.WriteLine(result.RecognitionText);
	}
}
```
{{< /tab >}}
{{< /tabs >}}
