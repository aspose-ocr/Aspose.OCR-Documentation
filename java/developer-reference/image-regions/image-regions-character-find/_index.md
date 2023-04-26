---
weight: 35
date: "2023-04-26"
author: "Vladimir Lapin"
type: docs
url: /java/image-regions-character-find/
feedback: OCRJAVA
title: Finding character bounding boxes
description: Character-by-character recognition and automatic detection of character bounding boxes inside images.
keywords:
- character
- symbol
- block
- rectangle
- area
- box
- boundary
- coordinates
---

Aspose.OCR for Java can perform character-by-character recognition and automatically detect bounding boxes of each recognized character using `RecognizeCharacters` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/asposeocr/) class.

The method returns a list of [`CharacterRecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/characterrecognitionresult/) objects containing each recognized character along with its coordinates in each image.

Property | Type | Description
-------- | ---- | -----------
`Characters` | `ArrayList<Character>` | A list of recognized characters and their coordinates (top-left corner, width and height).
`ImageIndex` | `int` | Sequence number of the image on the page. When working with single-page images, this value is always 0.
`Page` | `int` | Page number. When working with single-page images, this value is always 0.
`Source` | `string` | The full path or URL of the source file. If the file is [provided](/ocr/java/ocrinput/) as a `BufferedImage` object, `InputStream`, an array of pixels, or a Base64 string, this value will be empty.

## Example

The following code example shows how to detect characters in an image:

```java
AsposeOCR api = new AsposeOCR();
// Add an image to the recognition batch
OcrInput input  = new OcrInput(InputType.SingleImage, filters);
input.add("source.png");
// Detect and recognize characters
ArrayList<CharacterRecognitionResult> result =  api.RecognizeCharacters(input, DetectAreasMode.DOCUMENT, Language.None);
// Output recognized characters
for(Character c : result[0].Characters)
{
	System.out.println("Found character \"" + c.Value + "\" by coordinates: left - " + c.Coordinates.X + " | top - " + c.Coordinates.Y + " | width - " + c.Coordinates.Width + " | height - " + c.Coordinates.Height);
}
```
