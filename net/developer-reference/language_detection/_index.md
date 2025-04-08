---
weight: 32
date: "2025-02-28"
author: "Vladimir Lapin"
type: docs
url: /net/language_detection/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
title: Language detecton
description: How to detect the languages used on the provided image.
keywords:
- language
- locale
- detect
- find
---

{{% alert color="caution" %}} 
To use language detection, [install](/ocr/net/modules/) (**aspose-ocr-language-classification-v1**) advanced OCR model to your project.
{{% /alert %}}

Aspose.OCR for .NET can automatically identify the following languages and language families used on the provided image using `Aspose.OCR.DetectLanguages` method:

- Latin
- Cyrillic
- Arabic
- Chinese
- Japanese
- Korean
- Hindi
- Tamil
- Telugu
- Kannada

The method accepts the collection of images in any of the [supported formats](/ocr/net/supported-file-formats/) and returns them as a list of `Aspose.OCR.LanguageDetectionOutput` objects with the following properties:

Property    | Type                                             | Description
----------- | ------------------------------------------------ | -----------
`Source`    | `string`                                         | The full path or URL of the source file. If the file is provided as a `MemoryStream` object, an array of pixels, or a Base64 string, this value will be empty.
`Page`      | `int`                                            | Page number. When working with single-page images, this value is always 0.
`Languages` | `List<KeyValuePair<Aspose.OCR.Language, float>>` | Lists the [recognition languages](/ocr/net/languages/) detected in the image along with their probabilities.

## Example

The following code sample demonstrates how to detect the image languages:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Detect languages
List<Aspose.OCR.LanguageDetectionOutput> result = recognitionEngine.DetectLanguages(input);
foreach (Aspose.OCR.LanguageDetectionOutput item in result)
{
	Console.WriteLine($"Image: {item.Source}");
	foreach (KeyValuePair<Aspose.OCR.Language, float> lang in item.Languages)
	{
		Console.WriteLine($"Language: {lang.Key}: {lang.Value}");
	}
}
```


The following code sample demonstrates how to recognize the image with auto detection languages:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Detect languages
List<Aspose.OCR.RecognitionResult> result = recognitionEngine.Recognize(input, new RecognitionSettings { 
                Language = Aspose.OCR.Language.Auto,
                LanguageDetectionLevel = Aspose.OCR.LanguageDetectionLevel.ByParagraph
                });
foreach (Aspose.OCR.RecognitionResult item in result)
{
		Console.WriteLine($"Text: {item.RecognitionText}");
}
```
