---
weight: 100
date: "2023-07-14"
author: "Vladimir Lapin"
type: docs
url: /java/find-text/
feedback: OCRJAVA
title: Finding text in an image
description: How to determine if an image contains provided text.
keywords:
- find
- detect
- identify
- locate
- text
- string
---

Aspose.OCR for Java makes searching for text in images as easy as finding the text fragment in a string. In a single line of code, you can search for a case-sensitive or case-insensitive string, and even validate an image text against a pattern.

To search for a text in an image, use `ImageHasText` method of [`AsposeOcr`](https://reference.aspose.com/ocr/java/com.aspose.ocr/asposeocr/) class. The method either takes a text fragment or a regular expression and returns `true` if the text is found or `false` if not.

`ImageHasText` method allows you to optionally customize recognition accuracy, performance, and other [settings](/ocr/java/recognition-settings-common/).

```java
AsposeOCR api = new AsposeOCR();
if(!api.ImageHasText("image.png", "Aspose"))
{
	System.out.println("The image contains the word \"Aspose\"");
}
else
{
	System.out.println("The image doesn't contain the word \"Aspose\"");
}
```
