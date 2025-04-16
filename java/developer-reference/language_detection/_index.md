---
weight: 32
date: "2025-03-19"
author: "Vladimir Lapin"
type: docs
url: /java/language_detection/
feedback: OCRJAVA
title: Language detecton
description: How to detect the languages used on the provided image.
keywords:
- language
- locale
- detect
- find
---

{{% alert color="caution" %}} 
To use language detection, [install](/ocr/java/modules/) (**aspose-ocr-language-classification-v1**) advanced OCR model to your project.
{{% /alert %}}

Aspose.OCR for Java can automatically identify the following languages and language families used on the provided image using `DetectLanguages` method:

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

The method accepts the collection of images in any of the [supported formats](/ocr/java/supported-file-formats/) and returns them as a list of `LanguageDetectionOutput` objects with the following properties:

Property    | Type                               | Description
----------- | ---------------------------------- | -----------
`source`    | `string`                           | The full path or URL of the source file. If the file is [provided](/ocr/java/ocrinput/) as a `BufferedImage`, `InputStream`, an array of pixels, or a Base64 string, this value will be empty.
`page`      | `int`                              | Page number. When working with single-page images, this value is always 0.
`languages` | `List<Map.Entry<Language, Float>>` | Lists the [recognition languages](/ocr/java/languages/) detected in the image along with their probabilities.

## Example

The following code sample demonstrates how to detect the image languages:

```java
OcrInput input = new OcrInput(InputType.SingleImage);
input.add("source.png");
LanguageDetectionOutput result = api.DetectLanguages(input).get(0);
out.println("File: " + result.source);
out.println("Page: " + result.page);
for(Map.Entry<Language, Float> l : result.languages)
out.println("Language: " + l.getKey()+ " : " + l.getValue());
```

The following code sample demonstrates how to recognize the image with auto detection languages:

```java

AsposeOCR recognitionEngine = new AsposeOCR();
// Add an image to OcrInput object
OcrInput input = new OcrInput(InputType.SingleImage);
input.add("source.png");
// Set language detection and it is level.
RecognitionSettings settings = new RecognitionSettings();
settings.setLanguage(com.aspose.ocr.models.Language.Auto);
settings.setLanguageDetectionLevel(LanguageDetectionLevel.BY_PARAGRAPH);
		
// Recognize with detect languages
List<RecognitionResult> result = recognitionEngine.Recognize(input, );
for (RecognitionResult item : result)
{
    System.out.println("Text: "+item.recognitionText);
}
```
