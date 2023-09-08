---
weight: 10
date: "2023-08-25"
author: "Vladimir Lapin"
type: docs
url: /python-net/ocrinput/
feedback: OCRPYNET
title: Preparing content for recognition
description: How to prepare a batch of images, PDF documents, URLs and other content for recognition using Aspose.OCR for Python via .NET.
keywords:
- image
- PDF
- file
- folder
- batch
- list
---

Aspose.OCR for Python via .NET provides a versatile way to prepare your content for OCR. A package of recognized files/folders/URLs, regardless of their number and type, is constructed as [`OcrInput`](https://reference.aspose.com/ocr/python-net/aspose.ocr/ocrinput/) object. With this approach, you can easily process a single image or a large number of images from an auto-feed scanner in a [single API call](/ocr/python-net/recognition/).

The object constructor takes the [type](#supported-content-types) of the provided content and optional [processing filters](#applying-image-processing-filters) that will be applied to all images in a batch.

## Supported content types

You can only pack sources of the same type into one `OcrInput` object. The [type](https://reference.aspose.com/ocr/python-net/aspose.ocr/inputtype/) is specified in the constructor and cannot be changed later.

Source content type | Supported file formats
------------------- | ----------------------
`InputType.SINGLE_IMAGE` | One or more GIF, PNG, JPEG, BMP, or single-page TIFF images. The images can be provided by their absolute or relative paths, as `MemoryStream` objects, or as [arrays of pixels](/ocr/python-net/ocrinput/image-by-pixel/).<br />You can add images of different types in a single batch.
`InputType.PDF` | One or more PDF documents, containing scanned pages. The files can be provided by their absolute or relative paths or as `MemoryStream` objects.
`InputType.TIFF` | One or more multi-page TIFF images. The files can be provided by their absolute or relative paths or as `MemoryStream` objects.
`InputType.DJVU` | One or more DjVu files, provided by their absolute or relative paths or as `MemoryStream` objects.
`InputType.URL` | One or more web links to GIF, PNG, JPEG, BMP, or single-page TIFF images. Aspose.OCR for Python via .NET will download them automatically before processing.<br />**Limitations:**<ul><li>Aspose.OCR for Python via .NET does not support authentication and can only work with public URLs.</li><li>The URL must point directly to the image. Aspose.OCR for Python via .NET cannot extract images from HTML pages.</li></ul>
`InputType.DIRECTORY` | Absolute or relative paths to one or more folders containing GIF, PNG, JPEG, BMP, or single-page TIFF images. Unless specifically configured, all nested images will be recognized.<br />**Subfolders and nested archives will not be processed!**
`InputType.ZIP` | Absolute or relative paths to one or more ZIP archives containing GIF, PNG, JPEG, BMP, or single-page TIFF images. Unless specifically configured, all archived images will be recognized.<br />**Nested archives and folders will not be processed!**
`InputType.BASE64` | One or more GIF, PNG, JPEG, BMP, or single-page TIFF images provided as Base64-encoded strings.

{{% alert color="caution" %}}
Combination of different content types (for example, images and PDF documents) within one `OcrInput` object is not supported.
{{% /alert %}}

## Adding source content

To manage a batch of images, scanned PDFs, URLs, folders, and other OCR content, use the following methods of the `OcrInput` class:

Method | Purpose
------ | -------
`add(string)` | Adds an absolute or relative path to a file/folder, or a URL to an image file on the web.
`add(string, int, int)` | Adds an absolute or relative path to a multi-page image, PDF document, ZIP archive or folder, specifying the images/pages for recognition.
`add(stream)` | Adds a stream, containing a file to be recognized.
`add(stream, int, int)` | Adds a stream, containing a milti-page image, PDF document, or ZIP archive, specifying the images/pages for recognition.
`add(Color[], int, int)` | Adds an image provided as an [array of pixels](/ocr/python-net/ocrinput/image-by-pixel/#adding-image-as-asposedrawingcolor-array). You must specify the width and height.
`add(byte[], int, int, PixelType)` | Adds an image provided as an [array of pixels](/ocr/python-net/ocrinput/image-by-pixel/). You must specify the width, height and color model.
`add_base64(string)` | Adds an image encoded as Base64 string.

To get the number of items in the batch, use `count()` method.

## Removing source content

To remove all sources from a batch, use `clear()` method.

## Applying image processing filters

The accuracy and reliability of text recognition is highly dependent on the quality of the original image. Aspose.OCR for Python via .NET offers a large number of fully automated and manual image [processing filters](/ocr/python-net/image-processing/) that enhance an image before it is sent to the OCR engine.

To apply processing filters to all images in the batch, provide them in the `OcrInput` object constructor, or later using `replace_filters()` method.

To remove all processing filters from a batch, use `clear_filters()` method.

## Examples

The following code samples demonstrates how to prepare content for recognition:

{{< tabs tabID="1" tabTotal="3" tabName1="Provide multiple images" tabName2="Provide scanned PDF" tabName3="Apply processing filters" >}}
{{< tab tabNum="1" >}}
```python
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("page1.png")
input.add("page2.png")
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```python
input = OcrInput(InputType.PDF)
# Recognize pages 2 to 8
input.add("contract.pdf", 1, 7)
```
{{< /tab >}}
{{< tab tabNum="3" >}}
```python
# Automatically deskew all images
filters = PreprocessingFilter()
filters.add(PreprocessingFilter.auto_skew())
# Prepare batch
input = OcrInput(InputType.SINGLE_IMAGE, filters)
input.add("page1.png")
input.add("page2.png")
```
{{< /tab >}}
{{< /tabs >}}
