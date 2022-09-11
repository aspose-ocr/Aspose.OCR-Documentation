---
weight: 70
date: "2022-09-09"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/pixel/
title: Extracting text from pixel array
description: Extracting text from an image, provided as an array of bytes or an array of Aspose.Drawing.Color objects.
keywords:
- read
- extract
- OCR
- recognize
- pixel
- color
- byte
- array
---

Aspose.OCR allows you to provide an image for recognition as an array of pixels. This can be useful when working with [unsupported](/ocr/net/supported-file-formats/) image formats and passing the image to a web application as a byte array.

Pixels are listed from left to right (by line), and each line is added to the array from top to bottom.

![Color ordering](pixel-order.png)

## Recognizing color images

The image can be provided as a flat byte array representing the amount of each color per pixel. The amount can range from 0 to 255, where 0 means no that color and 255 is the maximum amount of that color.

Format | Bytes per pixel | Pixel color order
------ | :-------------: | ------------------
`Aspose.OCR.PixelType.RGB` | 3 | <ol><li>Red</li><li>Green</li><li>Blue</li></ol>
`Aspose.OCR.PixelType.BGR` | 3 | <ol><li>Blue</li><li>Green</li><li>Red</li></ol>
`Aspose.OCR.PixelType.RGBA` | 4 | <ol><li>Red</li><li>Green</li><li>Blue</li><li>Transparency</li></ol>

To recognize an image represented as an array of pixel colors, pass the array, image width and height, pixel color format, and optional recognition settings to [`RecognizeImage`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizeimage/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
using(Aspose.Imaging.RasterImage image = (RasterImage)Aspose.Imaging.Image.Load("source.png"))
{
	Color[] c = image.LoadPixels(image.Bounds);
	byte[] arr = new byte[c.Length*3];
	int idx = 0;
	for (int i = 0; i < c.Length*3; i += 3)
	{
		arr[i] = c[idx].R;
		arr[i+1] = c[idx].G;
		arr[i+2] = c[idx].B;
		idx++;
	}
	Aspose.OCR.RecognitionResult recognitionResult = recognitionEngine.RecognizeImage(pixels, image.Width, image.Height, Aspose.OCR.PixelType.RGB);
	Console.WriteLine(recognitionResult.RecognitionText);
}
```

## Recognizing grayscale images

The image is provided as a flat byte array representing the degree of pixel saturation (one byte per pixel). The number can range from 0 to 255, where 0 means black and 255 means white.

To recognize a grayscale image represented as an array of pixels, pass the following parameters to [`RecognizeImage`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizeimage/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class:

- Byte array;
- Image width and height;
- `Aspose.OCR.PixelType.BYTE`;
- Optional recognition settings.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
using(Aspose.Imaging.RasterImage image = (RasterImage)Aspose.Imaging.Image.Load("source.png"))
{
	Color[] c = image.LoadPixels(image.Bounds);
	byte[] arr = new byte[c.Length*3];
	for (int i = 0; i < c.Length; i++)
	{
		arr[i] = (byte)((c[i].R + c[i].G +c[i].B)/3);
	}
	Aspose.OCR.RecognitionResult recognitionResult = recognitionEngine.RecognizeImage(pixels, image.Width, image.Height, Aspose.OCR.PixelType.BYTE);
	Console.WriteLine(recognitionResult.RecognitionText);
}
```

## Recognizing images from Aspose.Drawing.Color array

The image is provided as an array of [`Aspose.Drawing.Color`](https://reference.aspose.com/drawing/net/system.drawing/color/) objects.

To recognize an image represented as an array of pixel colors, pass the array, image width and height, and optional recognition settings to [`RecognizeImage`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizeimage/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
using(Aspose.Imaging.RasterImage image = (RasterImage)Aspose.Imaging.Image.Load("source.png"))
{
	Color[] c = image.LoadPixels(image.Bounds);
	Aspose.Drawing.Color[] c1 = new Aspose.Drawing.Color[c.Length];
	for (int i = 0; i < c.Length; i++)
	{
		c1[i] = Aspose.Drawing.Color.FromArgb(c[i].R, c[i].G, c[i].B);
	}
	Aspose.OCR.RecognitionResult recognitionResult = recognitionEngine.RecognizeImage(c1, image.Width, image.Height);
	Console.WriteLine(recognitionResult.RecognitionText);
}
```
