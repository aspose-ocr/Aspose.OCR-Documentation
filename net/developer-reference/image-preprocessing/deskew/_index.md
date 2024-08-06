---
weight: 10
date: "2024-08-05"
author: "Vladimir Lapin"
type: docs
url: /net/deskew/
feedback: OCRNET
aliases:
- /net/working-with-the-skew-angle-of-the-image/
- /net/enable-or-disable-text-area-detection-and-skew-correction/
title: Skew correction
description: How to straighten a rotated image to improve recognition accuracy.
keywords:
- deskew
- straighten
- rotate
- tilt
- skew
- align
---

<style>
	button {
		cursor: pointer;
		margin-right: 20px;
		padding: 7px 15px;
		border: none;
		border-radius: 5px;
		background-color: #1a89d0;
		font-weight: 700;
		font-size: 15px;
		color: #ffffff;
	}

	button:hover {
		background-color: #3071a9;
	}

	button:focus {
		outline: none;
	}

	.code-sample {
		display: flex;
	}

	.code-sample > div {
		display: flex;
		align-items: center;
		padding: 5px 10px;
		border-radius: 5px;
		white-space: nowrap;
		background-color: rgba(0,0,0,5%);
		font-size: 16px;
		font-weight: 700;
	}

	.unseen {
		display: none !important;
	}

	.duo {
		position: relative;
		width: 800px;
		height: 474px;
	}

	.duo > img {
		position: absolute;
	}
</style>

When a page is fed to a flatbed scanner (mechanically or manually) or photographed with a smartphone, it is nearly impossible to achieve perfect alignment. As a result, a slight skew (tilt) inevitably occurs in scanned images or photographs.

Skew angle detection and image straightening is critical to the OCR process as it directly affects the reliability and efficiency of segmentation and text extraction. Aspose.OCR offers automated processing algorithms to correct image tilt (deskew) before proceeding to recognition.

## Detecting skew angles

To find out skew angles for all images in a [batch](/ocr/net/ocrinput/), use [`Aspose.OCR.AsposeOcr.CalculateSkew`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/calculateskew/) method. It returns a list of [`Aspose.OCR.SkewOutput`](https://reference.aspose.com/ocr/net/aspose.ocr/skewoutput/) objects, one per image.

Property | Type | Description
-------- | ---- | -----------
`Angle` | `float` | Skew angle in degrees.
`ImageIndex` | `int` | Sequence number of the image on the page. When working with single-page images, this value is always 0.
`Page` | `int` | Page number. When working with single-page images, this value is always 0.
`Source` | `string` | The full path or URL of the source file. If the file is provided as a `MemoryStream` object, an array of pixels, or a Base64 string, this value will be empty.

{{% alert color="primary" %}}
- Skew angles are calculated for all images in the batch, including those without text.
- PDF documents can contain more than one image per page. Therefore, the resulting list can contain more `Aspose.OCR.SkewOutput` objects than the number of pages in the document.
{{% /alert %}}

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add PDF documents to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(InputType.PDF);
input.Add("source.pdf");
// Detect skew angles
List<Aspose.OCR.SkewOutput> angles = recognitionEngine.CalculateSkew(input);
foreach(Aspose.OCR.SkewOutput angle in angles) Console.WriteLine($"File: {angle.Source} | Page: {angle.Page} | Image: {angle.ImageIndex} | Angle: {angle.Angle}°");
```

![Skewed image](skew-origin.png)

<div id="skew-angle" class="code-sample">
	<button onclick="calculateSkewAngle(this)">Calculate skew angle</button>
	<div class="unseen"><code>&gt; File: "C:\source.pdf" | Page: 0 | Image: 0 | Angle: 5.9°</code></div>
</div>
<script>
	function calculateSkewAngle(obj)
	{
		$(obj).siblings("div").removeClass("unseen");
	}
</script>

## Automatic skew correction

To automatically straighten skewed image or rotate upside-down images before recognition, run the image through [`AutoSkew`](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/autoskew/) processing filter.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Enable automatic skew correction
Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter filters = new Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter();
filters.Add(Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter.AutoSkew());
// Add an image to OcrInput object and apply processing filters
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage, filters);
input.Add("source.png");
// Save processed image to the folder
Aspose.OCR.ImageProcessing.Save(input, @"C:\result");
// Recognize image
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```

<div class="duo">
	<img src="skew-origin.png" alt="Skewed image" />
	<img src="deskew.png" alt="Deskewed image" style="display: none;" />
</div>
<button onclick="triggerSkew(this)">Deskew image</button>
<script>
	function triggerSkew(obj)
	{
		let images = $(".duo > img");
		let skewed = images.eq(0).is(":visible");
		if(skewed)
		{
			images.eq(1).show(200);
			images.eq(0).hide(200);
			$(obj).text("Revert to original image");
		}
		else
		{
			images.eq(0).show(200);
			images.eq(1).hide(200);
			$(obj).text("Deskew image");
		}
	}
</script>

## Manual skew correction

In some edge cases, automatic skew correction may not detect the angle of the image. This can happen with poor quality photographs with significant perspective distortion.

To deal with such situations, you can rotate the image by the specified degree using [`Rotate`](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/rotate/) image processing filter. The rotation angle is passed in degrees:

- `-360` to `0`: rotate counterclockwise;
- `0` to `360`: rotate clockwise.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Rotate the image 90 degrees counterclockwise
Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter filters = new Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter();
filters.Add(Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter.Rotate(-90));
// Add an image to OcrInput object and apply processing filters
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage, filters);
input.Add("source.png");
// Save processed image to the folder
Aspose.OCR.ImageProcessing.Save(input, @"C:\result");
// Recognize image
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```

## Image regions processing

Automatic skew correction and manual rotation filters can be applied to specific regions of an image. For example, you can straighten an illustration on a page while leaving the rest of the content unchanged.

{{% alert color="primary" %}} 
The original size of an image does not change when its area is rotated. Parts of the rotated area that do not match the original size of the area are cropped.

It is recommended to apply the automatic deskew and manual rotation filters only to square areas.
{{% /alert %}}

To apply a filter to an area, specify its top left corner along with width and height as [`Aspose.Drawing.Rectangle`](https://reference.aspose.com/drawing/net/system.drawing/rectangle/) object. If the region is omitted, the filter is applied to the entire image.

```csharp
Aspose.Drawing.Rectangle rectangle = new Aspose.Drawing.Rectangle(5, 161, 340, 340);
Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter filters = new Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter();
filters.Add(Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter.Rotate(90, rectangle));
```

## Usage scenarios

- Automatic skew correction is recommended in almost all cases, except for perfectly straight scans.
- Manual rotation is recommended for:
    - photos of low quality;
    - images with a significant angle of inclination.
