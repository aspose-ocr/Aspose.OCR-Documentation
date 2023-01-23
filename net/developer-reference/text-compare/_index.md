---
weight: 62
date: "2023-01-20"
author: "Vladimir Lapin"
type: docs
url: /net/image-text-compare/
title: Comparing text in images
description: How to compare texts on two images.
keywords:
- compare
- similar
- difference
- diff
- text
---

Aspose.OCR for .NET can compare texts on two images, regardless of the font, text size, case, styles, and colors.

To compare texts in 2 images, use [`ImageTextDiff`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/imagetextdiff/) method of [`AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class. This method allows you to optionally customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-image/).

`ImageTextDiff` returns a number representing how similar the compared images are. The return value is a floating point number from 0 to 1; the lower the number, the more different image texts are. **0** means that the texts are completely different; **1** means the texts are identical. Fonts and styles are ignored.

{{% alert color="primary" %}}
The difference between image texts is calculated as the [Levenshtein distance](https://en.wikipedia.org/wiki/Levenshtein_distance). Simply put, it is the minimum number of changes required to transform one string into another by inserting, deleting or replacing a single character.
{{% /alert %}}

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.AutoDenoising = true;
// case-insensitive comparison of image texts
if(!recognitionEngine.CompareImageTexts("image1.png", "image2.png", recognitionSettings, true))
{
	Console.WriteLine("Images contain the same text");
}
// percentage of similarity between texts
else
{
	float distance = recognitionEngine.ImageTextDiff("image1.png", "image2.png", recognitionSettings, true);
	Console.WriteLine($"The image texts are {distance*100}% similar");
}
```
