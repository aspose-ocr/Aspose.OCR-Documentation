---
weight: 10
date: "2023-04-05"
author: "Vladimir Lapin"
type: docs
url: /net/ocrinput/
feedback: OCRNET
title: Preparing content for recognition
description: How to prepare a batch of images, PDF documents, URLs and other content for recognition.
keywords:
- image
- PDF
- file
- folder
- batch
- list
---

Aspose.OCR for .NET provides a versatile way to prepare your content for OCR. A package of recognized files/folders/URLs, regardless of their number and type, is constructed as an instance of the [`Aspose.OCR.OcrInput`](https://reference.aspose.com/ocr/net/aspose.ocr/ocrinput/) class. With this approach, you can easily process a single image or a large number of images from an auto-feed scanner in a [single API call](/ocr/net/recognition/).

The object constructor takes the [type](#supported-content-types) of the provided content and optional [processing filters](#applying-image-processing-filters) that will be applied to all images in a batch.

## Supported content types

You can only pack sources of the same type into one instance of the [`Aspose.OCR.OcrInput`](https://reference.aspose.com/ocr/net/aspose.ocr/ocrinput/) class. The [type](https://reference.aspose.com/ocr/net/aspose.ocr/inputtype/) is specified in the constructor and cannot be changed later.

Source content type | Supported file formats
------------------- | ----------------------
`Aspose.OCR.InputType.SingleImage` | One or more GIF, PNG, JPEG, BMP, or single-page TIFF images. The images can be provided by their absolute or relative paths, as `MemoryStream` objects, or as [arrays of pixels](/ocr/net/ocrinput/image-by-pixel/).<br />You can add images of different types in a single batch.
`Aspose.OCR.InputType.PDF` | One or more PDF documents, containing scanned pages. The files can be provided by their absolute or relative paths or as `MemoryStream` objects.
`Aspose.OCR.InputType.TIFF` | One or more multi-page TIFF images. The files can be provided by their absolute or relative paths or as `MemoryStream` objects.
`Aspose.OCR.InputType.DJVU` | One or more DjVu files, provided by their absolute or relative paths or as `MemoryStream` objects.
`Aspose.OCR.InputType.URL` | One or more web links to GIF, PNG, JPEG, BMP, or single-page TIFF images. Aspose.OCR for .NET will download them automatically before processing.<br />**Limitations:**<ul><li>Aspose.OCR for .NET does not support authentication and can only work with public URLs.</li><li>The URL must point directly to the image. Aspose.OCR for .NET cannot extract images from HTML pages.</li></ul>
`Aspose.OCR.InputType.Directory` | Absolute or relative paths to one or more folders containing GIF, PNG, JPEG, BMP, or single-page TIFF images. Unless specifically configured, all nested images will be recognized.<br />**Subfolders and nested archives will not be processed!**
`Aspose.OCR.InputType.Zip` | Absolute or relative paths to one or more ZIP archives containing GIF, PNG, JPEG, BMP, or single-page TIFF images. Unless specifically configured, all archived images will be recognized.<br />**Nested archives and folders will not be processed!**
`Aspose.OCR.InputType.Base64` | One or more GIF, PNG, JPEG, BMP, or single-page TIFF images provided as Base64-encoded strings.

{{% alert color="caution" %}}
Combination of different content types (for example, images and PDF documents) is not supported.
{{% /alert %}}

## Adding source content

To manage a batch of images, scanned PDFs, URLs, folders, and other OCR content, use the following methods of the [`Aspose.OCR.OcrInput`](https://reference.aspose.com/ocr/net/aspose.ocr/ocrinput/) class:

Method | Description
------ | -----------
`Add(string)` | Add an absolute or relative path to a file/folder, or a URL to an image file on the web.
`Add(string, int, int)` | Add an absolute or relative path to a multi-page image, PDF document, ZIP archive or folder, specifying the images/pages for recognition.
`Add(MemoryStream)` | Add a `MemoryStream` object, containing a file to be recognized.
`Add(MemoryStream, int, int)` | Add a `MemoryStream` object, containing a milti-page image, PDF document, or ZIP archive, specifying the images/pages for recognition.
`Add(Color[], int, int)` | Add an image provided as an [array of pixels](/ocr/net/ocrinput/image-by-pixel/#adding-image-as-asposedrawingcolor-array). You must specify the width and height.
`Add(byte[], int, int, PixelType)` | Add an image provided as an [array of pixels](/ocr/net/ocrinput/image-by-pixel/). You must specify the width, height and color model.
`AddBase64(string)` | Add an image encoded as Base64 string.

To get the number of items in the batch, use [`Count()`](https://reference.aspose.com/ocr/net/aspose.ocr/ocrinput/count/) method of the [`Aspose.OCR.OcrInput`](https://reference.aspose.com/ocr/net/aspose.ocr/ocrinput/) class.

## Removing source content

To clear a batch, use [`Clear()`](https://reference.aspose.com/ocr/net/aspose.ocr/ocrinput/clear/) or [`Dispose()`](https://reference.aspose.com/ocr/net/aspose.ocr/ocrinput/dispose/) methods of the [`Aspose.OCR.OcrInput`](https://reference.aspose.com/ocr/net/aspose.ocr/ocrinput/) class.

## Applying image processing filters

The accuracy and reliability of text recognition is highly dependent on the quality of the original image. Aspose.OCR for .NET offers a large number of fully automated and manual image [processing filters](/ocr/net/image-processing/) that enhance an image before it is sent to the OCR engine.

To apply processing filters to all images in the batch, provide them in the [`Aspose.OCR.OcrInput` object constructor](https://reference.aspose.com/ocr/net/aspose.ocr/ocrinput/ocrinput/), or later using [`ReplaceFilters()`](https://reference.aspose.com/ocr/net/aspose.ocr/ocrinput/replacefilters/) method.

To remove all processing filters from a batch, use [`ClearFilters()`](https://reference.aspose.com/ocr/net/aspose.ocr/ocrinput/clearfilters/) method of the [`Aspose.OCR.OcrInput`](https://reference.aspose.com/ocr/net/aspose.ocr/ocrinput/) class.

## Examples

The following code samples demonstrates how to prepare content for recognition:

{{< tabs tabID="1" tabTotal="3" tabName1="Provide multiple images" tabName2="Provide scanned PDF" tabName3="Apply processing filters" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.OcrInput source = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
source.Add("image1.png");
source.Add("image2.jpg");
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.OcrInput source = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.PDF);
// Recognize pages 2 to 8
source.Add("scan.pdf", 1, 7);
```
{{< /tab >}}
{{< tab tabNum="3" >}}
```csharp
// Automatically deskew all images
Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter filters = new Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter();
filters.Add(Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter.AutoSkew());
// Prepare batch
Aspose.OCR.OcrInput source = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage, filters);
source.Add("image1.png");
source.Add("image2.jpg");
```
{{< /tab >}}
{{< /tabs >}}
