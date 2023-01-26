---
weight: 121
date: "2023-01-16"
author: "Vladimir Lapin"
type: docs
url: /java/aspose-ocr-for-net-23-1-0-release-notes/
feedback: OCRJAVA
title: Aspose.OCR for Java 23.1.0 - Release Notes
description: A summary of recent changes, enhancements and bug fixes in Aspose.OCR for Java 23.1.0 (January 2023) release.
keywords:
- 2023
- January
- new
- release
- changelog
---

{{% alert color="primary" %}}
This article contains a summary of recent changes, enhancements and bug fixes in [**Aspose.OCR for Java 23.1.0 (January 2023)**](https://www.nuget.org/packages/Aspose.OCR/23.1.0) release.

GPU version: **21.6.0**
{{% /alert %}}

## What was changed

Key | Summary | Category
--- | ------- | --------
OCRJAVA-298 | Hindi language support. | New feature
OCRJAVA-301 | Saving recognition results in RTF format. | New feature
OCRJAVA-301 | Saving recognition results in HTML format. | New feature
OCRJAVA-301 | Saving recognition results in EPUB format. | New feature

## Public API changes and backwards compatibility

This section lists all public API changes introduced in **Aspose.OCR for Java 23.1.0** that may affect the code of existing applications.

### Added public APIs:

The following public APIs have been introduced in this release:

#### Hindi language support

Extract text in Hindi language by providing `Language.Hin` value to `setLanguage()` method of [recognition settings](/ocr/java/settings/).

#### New file formats for recognition results

Added new file formats for [saving](/ocr/java/save-file/) recognition results:

Value | File format | Description
----- | ----------- | -----------
`Format.Html` | HTML | Web page.
`Format.Epub` | ePub | Popular e-book file format.
`Format.Rtf` | RTF | A universal format for exchanging text documents between different word processing programs.

### Updated public APIs:

_No changes._

### Removed public APIs:

_No changes._

## Usage examples

The examples below illustrates the changes introduced in this release:

### Reading Hindi images

```java
AsposeOCR api = new AsposeOCR();
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setLanguage(Language.Hin);
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```

### Saving recognition results to ePUB

```java
AsposeOCR api = new AsposeOCR();
ArrayList<RecognitionResult> results = api.RecognizeMultiplePages("images.zip", new RecognitionSettings());
api.SaveMultipageDocument("result.pdf", Format.Epub, results);
```
