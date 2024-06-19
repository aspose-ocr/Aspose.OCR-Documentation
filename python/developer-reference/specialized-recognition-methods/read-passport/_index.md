---
weight: 20
date: "2024-06-19"
author: "Vladimir Lapin"
type: docs
url: /python-net/recognition/passport/
feedback: OCRPYNET
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

Aspose.OCR for Python via .NET offers a special recognition algorithm that extracts text from scanned or photographed passports, which can then be automatically saved to the database or automatically verified.

To extract text from a passport image, use `recognize_passport()` method of [`AsposeOcr`](https://reference.aspose.com/ocr/python-net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/python-net/recognition-settings-passport/).

The method takes [`OcrInput` object](/ocr/python-net/ocrinput/) and returns a [`RecognitionResult`](https://reference.aspose.com/ocr/python-net/aspose.ocr/recognitionresult/) object containing the passport data.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("passport1.png")
input.add("passport2.png")
# Set recognition language
recognitionSettings = PassportRecognitionSettings()
recognitionSettings.language = Language.Latin
# Recognize passports
results = api.recognize_passport(input, recognitionSettings)
# Print recognition result
for result in results:
    print(result.recognition_text)
```

## Extracting passport details

Besides recognizing passport text, this method is capable of extracting essential information from a passport image, like date of birth, names, and more. The specific details extracted depend on the passport's origin, which is specified in the `country` parameter of the [recognition settings](/ocr/python-net/recognition-settings-passport/).

To retrieve the passport details, use the `get_keywords()` method of the recognition results object. The information is returned as a collection of `Keyword` objects, representing a single passport detail as a name-value pair:

- `key` - passport detail ID, for example `DATE_OF_BIRTH`;
- `value` - specific passport detail, for example `1 Sep 2000`

### Example

The following code snippet shows how to extract key details from US passport:

```python
# Instantiate Aspose.OCR API
api = ocr.AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("us_passport.png")
# Enable US passport recognition
settings = ocr.PassportRecognitionSettings()
settings.country = ocr.Country.USA
# Extract passport details
result = api.recognize_passport(input, settings)
details = result[0].get_keywords()
for detail in details:
    print(detail.key)
    print(detail.value.text_in_line)
```
