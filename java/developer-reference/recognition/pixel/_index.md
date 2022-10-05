---
weight: 70
date: "2022-09-29"
author: "Vladimir Lapin"
type: docs
url: /java/recognition/pixel/
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

Aspose.OCR allows you to provide an image for recognition as an array of pixels. This can be useful when working with [unsupported](/ocr/java/supported-file-formats/) image formats and passing the image to a web application as a byte array.

Pixels are listed as a flat array of integers from left to right (by line), and each line is added to the array from top to bottom. Each element of the array represents the amount of each color (in the _red_ -> _green_ -> _blue_ order) per pixel. The amount can range from 0 to 255, where 0 means no that color and 255 is the maximum amount of that color.

![Color ordering](pixel-order-rgb.png)

To recognize an image represented as an array of pixel colors pass the array, image width and height, color depth (bits per pixel, from _1_ to _32_), and [recognition settings](/ocr/java/recognition-settings-image/) to `RecognizePage` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class:

```java
AsposeOCR api = new AsposeOCR();
// Load image
URL resFile =	getClass().getClassLoader().getResource("source.bmp");
com.aspose.imaging.Image image = com.aspose.imaging.Image.load(resFile.getFile());
// Recognize the image and output text
try {
	com.aspose.imaging.RasterImage rasterImage = (com.aspose.imaging.RasterImage) image;
	int[] pixels = rasterImage.loadArgb32Pixels(rasterImage.getBounds());  
	RecognitionResult res = api.RecognizePage(pixels, rasterImage.getWidth(), rasterImage.getHeight(), rasterImage.getBitsPerPixel(), new RecognitionSettings());
	System.out.println("Recognition result:\n" + result + "\n\n");
} finally {
	image.dispose(); 
}
```
