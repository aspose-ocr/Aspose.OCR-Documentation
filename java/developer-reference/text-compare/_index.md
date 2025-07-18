---
weight: 90
date: "2023-07-14"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /java/image-text-compare/
feedback: OCRJAVA
title: Comparing text in images
description: How to compare texts on two images.
keywords:
- compare
- similar
- difference
- diff
- text
---

Aspose.OCR for Java can compare texts on two images, regardless of the font, text size, case, styles, and colors.

To simply find out if two images contain the same text, use the `CompareImageTexts` method of the [`AsposeOcr`](https://reference.aspose.com/ocr/java/com.aspose.ocr/asposeocr/) class. To find the degree of similarity between texts in images, use the `ImageTextDiff` method of the [`AsposeOcr`](https://reference.aspose.com/ocr/java/com.aspose.ocr/asposeocr/) class. These methods allow you to further fine-tune recognition accuracy, performance, and other [settings](/ocr/java/recognition-settings-common/).

{{% alert color="primary" %}}
You can perform case-sensitive or case-insensitive comparison. Set the `ignoreCase` parameter to `true` to perform a case-insensitive comparison.
{{% /alert %}}

`ImageTextDiff` returns a number representing how similar the compared images are. The return value is a floating point number from 0 to 1; the lower the number, the more different image texts are. **0** means that the texts are completely different; **1** means the texts are identical. Fonts and styles are ignored. The difference between image texts is calculated as the [Levenshtein distance](https://en.wikipedia.org/wiki/Levenshtein_distance). Simply put, it is the minimum number of changes required to transform one string into another by inserting, deleting or replacing a single character.

```java
AsposeOCR api = new AsposeOCR();
// case-insensitive comparison of image texts
if(!api.CompareImageTexts("image1.png", "image2.png"))
{
	System.out.println("Images contain the same text");
}
// percentage of similarity between texts
else
{
	float distance = api.ImageTextDiff("image1.png", "image2.png");
	System.out.println("The image texts are " + (distance*100) + "% similar");
}
```
