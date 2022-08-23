---
weight: 50
date: "2022-08-22"
author: "Vladimir Lapin"
type: docs
url: /net/characters/
title: Defining recognized characters
description: Defining allow- and denylist of characters that Aspose.OCR looks for.
keywords:
- whitelist
- blacklist
- symbols
- characters
- letters
- probability
- allow
- deny
---

Aspose.OCR supports a [large list](/ocr/net/recognition-languages/) of extended Latin, Cyrillic, and Chinese characters. However, a typical image contains no more than half of these characters. You can greatly improve the accuracy and performance of recognition by specifying which characters the OCR engine will look for.

The full workflow is as follows:

1. [Identifying the characters on an image.](/ocr/net/characters-identify/)  
   Aspose.OCR provides detailed information about the characters found in the image and their possible alternatives.
2. [Defining the whitelist of characters.](/ocr/net/characters-whitelist/)  
   Limit the set of characters Aspose.OCR engine will look for.
3. [Defining the blacklist of characters.](/ocr/net/characters-blacklist/)  
   Explicitly ignore certain image defects that may be incorrectly recognized as characters.
