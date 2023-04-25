---
weight: 35
date: "2023-04-24"
author: "Vladimir Lapin"
type: docs
url: /net/image-regions-character-find/
feedback: OCRNET
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

Aspose.OCR for .NET can perform character-by-character recognition and automatically detect bounding boxes of each recognized character using [`Aspose.OCR.AsposeOcr.RecognizeCharacters`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizecharacters/) method.

The method returns a list of [`Aspose.OCR.CharacterRecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/characterrecognitionresult/) objects containing each recognized character along with its coordinates in each image.

Property | Type | Description
-------- | ---- | -----------
`Characters` | `List<Aspose.OCR.Character>` | A list of recognized characters and their coordinates (top-left corner, width and height).
`ImageIndex` | `int` | Sequence number of the image on the page. When working with single-page images, this value is always 0.
`Page` | `int` | Page number. When working with single-page images, this value is always 0.
`Source` | `string` | The full path or URL of the source file. If the file is provided as a `MemoryStream` object, an array of pixels, or a Base64 string, this value will be empty.

## Example

The following code example shows how to detect characters in an image:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to the recognition batch
Aspose.OCR.OcrInput source = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
source.Add("image1.png");
// Detect and recognize characters
List<Aspose.OCR.CharacterRecognitionResult> result = recognitionEngine.RecognizeCharacters(source, Aspose.OCR.DetectAreasMode.COMBINE)
// Output recognized characters
foreach(Aspose.OCR.Character c in result[0].Characters)
{
	Console.WriteLine($@"Found character ""{c.Value}"" by coordinates: left - {c.Coordinates.X} | top - {c.Coordinates.Y} | width - {c.Coordinates.Width} | height - {c.Coordinates.Height}");
}
```
