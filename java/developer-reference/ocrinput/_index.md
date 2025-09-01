---
weight: 10
date: "2023-04-26"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /java/ocrinput/
feedback: OCRJAVA
title: Preparing content for recognition
description: How to prepare a batch of images, PDF documents, URLs and other content for recognition.
keywords:
- image
- PDF
- file
- folder
- directory
- batch
- list
---

Aspose.OCR for Java provides a versatile way to prepare your content for OCR. A package of recognized files/directories/URLs, regardless of their number and type, is constructed as an instance of the [`OcrInput`](https://reference.aspose.com/ocr/java/com.aspose.ocr/ocrinput/) class. With this approach, you can easily process a single image or a large number of images from an auto-feed scanner in a [single API call](/ocr/java/recognition/).

The object constructor takes the [type](#supported-content-types) of the provided content and optional [processing filters](#applying-image-processing-filters) that will be applied to all images in a batch.

## Supported content types

You can only pack sources of the same type into one instance of the [`OcrInput`](https://reference.aspose.com/ocr/java/com.aspose.ocr/ocrinput/) class. The [type](https://reference.aspose.com/ocr/java/com.aspose.ocr/inputtype/) is specified in the constructor and cannot be changed later.

Source content type | Supported file formats
------------------- | ----------------------
`InputType.SingleImage` | One or more GIF, PNG, JPEG, BMP, or single-page TIFF images. The images can be provided by their absolute or relative paths, as `BufferedImage` objects, or as [arrays of pixels](/ocr/java/ocrinput/image-by-pixel/).<br />You can add images of different types in a single batch.
`InputType.PDF` | One or more PDF documents, containing scanned pages. The files can be provided by their absolute or relative paths or as `BufferedImage` objects.
`InputType.TIFF` | One or more multi-page TIFF images. The files can be provided by their absolute or relative paths or as `BufferedImage` objects.
`InputType.DJVU` | One or more DjVu files, provided by their absolute or relative paths or as `BufferedImage` objects.
`InputType.URL` | One or more web links to GIF, PNG, JPEG, BMP, or single-page TIFF images. Aspose.OCR for Java will download them automatically before processing.<br />**Limitations:**<ul><li>Aspose.OCR for Java does not support authentication and can only work with public URLs.</li><li>The URL must point directly to the image. Aspose.OCR for Java cannot extract images from HTML pages.</li></ul>
`InputType.Directory` | Absolute or relative paths to one or more directories containing GIF, PNG, JPEG, BMP, or single-page TIFF images. Unless specifically configured, all nested images will be recognized.<br />**Subdirectories and nested archives will not be processed!**
`InputType.Zip` | Absolute or relative paths to one or more ZIP archives containing GIF, PNG, JPEG, BMP, or single-page TIFF images. Unless specifically configured, all archived images will be recognized.<br />**Nested archives and directories will not be processed!**
`InputType.Base64` | One or more GIF, PNG, JPEG, BMP, or single-page TIFF images provided as Base64-encoded strings.

{{% alert color="caution" %}}
Combination of different content types (for example, images and PDF documents) within a single `OcrInput` object is not supported.
{{% /alert %}}

## Adding source content

To manage a batch of images, scanned PDFs, URLs, directories, and other OCR content, use the following methods of the [`OcrInput`](https://reference.aspose.com/ocr/java/com.aspose.ocr/ocrinput/) class:

Method | Description
------ | -----------
`add(string)` | Add an absolute or relative path to a file/directory, or a URL to an image file on the web.
`add(string, int, int)` | Add an absolute or relative path to a multi-page image, PDF document, ZIP archive or directory, specifying the images/pages for recognition.
`add(BufferedImage)` | Add a `BufferedImage` object, containing a file to be recognized.
`add(BufferedImage, int, int)` | Add a `BufferedImage` object, containing a milti-page image, PDF document, or ZIP archive, specifying the images/pages for recognition.
`add(InputStream)` | Add a `InputStream` stream, containing a file to be recognized.
`add(InputStream, int, int)` | Add a `InputStream` stream, containing a milti-page image, PDF document, or ZIP archive, specifying the images/pages for recognition.
`add(int[], int, int, PixelType)` | Add an image provided as an [array of pixels](/ocr/java/ocrinput/image-by-pixel/). You must specify the width, height and the color depth (number of bits per pixel).
`addBase64(string)` | Add an image encoded as Base64 string.

To get the number of items in the batch, use [`size()`](https://reference.aspose.com/ocr/java/com.aspose.ocr/ocrinput/#size--) method of the [`OcrInput`](https://reference.aspose.com/ocr/java/com.aspose.ocr/ocrinput/) class.

## Removing source content

To clear a batch, use [`clear()`](https://reference.aspose.com/ocr/java/com.aspose.ocr/ocrinput/#clear--) method of the [`OcrInput`](https://reference.aspose.com/ocr/java/com.aspose.ocr/ocrinput/) class.

## Applying image processing filters

The accuracy and reliability of text recognition is highly dependent on the quality of the original image. Aspose.OCR for Java offers a large number of fully automated and manual image [processing filters](/ocr/net/image-processing/) that enhance an image before it is sent to the OCR engine.

To apply processing filters to all images in the batch, provide them in the [`OcrInput` object constructor](https://reference.aspose.com/ocr/java/com.aspose.ocr/ocrinput/#OcrInput-com.aspose.ocr.InputType-com.aspose.ocr.PreprocessingFilter-), or later using [`replaceFilters()`](https://reference.aspose.com/ocr/java/com.aspose.ocr/ocrinput/#replaceFilters-com.aspose.ocr.PreprocessingFilter-) method.

To remove all processing filters from a batch, use [`clearFilters()`](https://reference.aspose.com/ocr/java/com.aspose.ocr/ocrinput/#clearFilters--) method of the [`OcrInput`](https://reference.aspose.com/ocr/java/com.aspose.ocr/ocrinput/) class.

## Examples

The following code samples demonstrates how to prepare content for recognition:

{{< tabs tabID="1" tabTotal="3" tabName1="Provide multiple images" tabName2="Provide scanned PDF" tabName3="Apply processing filters" >}}
{{< tab tabNum="1" >}}
```java
OcrInput source = new OcrInput(InputType.SingleImage);
source.add("image1.png");
source.add("image2.jpg");
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```java
OcrInput source = new OcrInput(InputType.PDF);
// Recognize pages 2 to 8
source.add("scan.pdf", 1, 7);
```
{{< /tab >}}
{{< tab tabNum="3" >}}
```java
// Automatically deskew all images
PreprocessingFilter filters = new PreprocessingFilter();
filters.add(Models.PreprocessingFilters.PreprocessingFilter.AutoSkew());
// Prepare batch
OcrInput source = new OcrInput(InputType.SingleImage, filters);
source.add("image1.png");
source.add("image2.jpg");
```
{{< /tab >}}
{{< /tabs >}}
