---
weight: 51
date: "2022-10-31"
author: "Alex Golshtein"
type: docs
url: /net/aspose-ocr-for-net-22-10-release-notes/
title: Aspose.OCR for .NET 22.10 - Release Notes
description: A summary of recent changes, enhancements and bug fixes in Aspose.OCR for .NET 22.10 (October 2022) release.
keywords:
- 2022
- October
- new
- release
- changelog
---

{{% alert color="primary" %}}

This article contains a summary of recent changes, enhancements and bug fixes in [**Aspose.OCR for .NET 22.10 (October 2022)**](https://www.nuget.org/packages/Aspose.OCR/22.10.0) release.

GPU version: **22.10.0**

{{% /alert %}}

## What was changed

Key | Summary | Category
--- | ------- | --------
OCRNET-600 | Deserialization of “RecognitionResult” object fail to Restore the original object. Extend fields for correct serialization. | Enhancement
OCRNET-584 | Add methods for recognize TIFF and DJVU images from MemoryStream (Can you provide a memory stream over load for RecognizeTiff() too) | Feature
OCRNET-592 | Fix TIFF image with different horizontal and vertical resolution recognition (Tiff image is getting distorted pdf after Processing | Bug fix
OCRNET-595 | Fix empty page processing during recognition (System.IndexOutOfRangeException in Aspose.OCR.dll) | Bug fix

### Changes in the release 22.10
- added RecognizeTiff and RecognizeDjvu from MemoryStream
- fixed recognition TIFFs with different horizontal and vertical resolution
- removed obsolete methods

(List<string> RecognizeImage(string fullPath, List<Aspose.Drawing.Rectangle> textAreas)

string RecognizeImage(MemoryStream stream, bool detectAreas, bool autoSkew = true)

RecognizeImage(MemoryStream stream, List<Aspose.Drawing.Rectangle> textAreas))

string RecognizeImage(string fullPath, bool detectAreas, bool autoSkew = true)

- obsolete DetectAreas setting
