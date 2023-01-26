---
weight: 30
date: "2022-09-23"
author: "Vladimir Lapin"
type: docs
url: /java/characters-blacklist/
feedback: OCRJAVA
aliases:
- /java/provide-ignored-characters-during-ocr-operation/
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

To ignore certain characters during recognition, provide them in [`setIgnoredCharacters`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setIgnoredCharacters-java.lang.String-) method of [recognition settings](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings) object as a case-sensitive string:

```java
AsposeOCR api = new AsposeOCR();
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setIgnoredCharacters("Áá");
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```
