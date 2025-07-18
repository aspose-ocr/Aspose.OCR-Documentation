---
weight: 32
date: "2025-03-03"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/language_detection/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRPYNET
title: Language detecton
description: How to detect the languages used on the provided image.
keywords:
- language
- locale
- detect
- find
---

{{% alert color="caution" %}} 
To use language detection, [install](/ocr/python-net/modules/) (**aspose-ocr-language-classification-v1**) advanced OCR model to your project.
{{% /alert %}}

Aspose.OCR for .NET can automatically identify the following languages and language families used on the provided image using `detect_languages` method:

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

The method accepts the collection of images in any of the [supported formats](/ocr/python-net/supported-file-formats/) and returns them as an array of `LanguageDetectionOutput` objects with the following properties:

Property    | Type                                | Description
----------- | ----------------------------------- | -----------
`source`    | `string`                            | The full path or URL of the source file. If the file is provided as a `MemoryStream` object, an array of pixels, or a Base64 string, this value will be empty.
`page`      | `int`                               | Page number. When working with single-page images, this value is always 0.
`languages` | Array of `DetectedLanguage` objects | Lists the [recognition languages](/ocr/python-net/languages/) detected in the image along with their probabilities.

`DetectedLanguage` objects contain the following properties:

Property    | Type       | Description
----------- | ---------- | -----------
`language ` | `Language` | [Detected language](/ocr/python-net/languages/)
`accuracy ` | `float`    | The confidence level of the language detection, which can be used to assess the accuracy.

## Example

The following code sample demonstrates how to detect the image languages:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Detect languages
result = api.detect_languages(input)
for lang in result[0].languages:
    print(lang.language)
    print(lang.accuracy)
```

The following code sample demonstrates how to detect the image languages and recognize multilanguage image:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Set language detection
set = RecognitionSettings()
set.language = Language.AUTO
set.language_detection_level = LanguageDetectionLevel.BY_WORD
# Detect languages and recognize image     
results = api.recognize(input, set)
for result in results:
    print(result.recognition_text)
```
