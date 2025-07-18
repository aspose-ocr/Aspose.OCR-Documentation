---
weight: 40
date: "2023-08-26"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/characters/
feedback: OCRPYNET
title: Defining recognized characters
description: Defining allow- and denylist of characters that Aspose.OCR for Python via .NET looks for.
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

Aspose.OCR for Python via .NET supports a [large list](/ocr/python-net/recognition-languages/) of extended Latin, Cyrillic and Asian characters. However, a typical image contains no more than half of these characters. You can greatly improve the accuracy and performance of recognition by specifying which characters the OCR engine will look for.

The full workflow is as follows:

1. [Identifying the characters on an image.](/ocr/python-net/characters-identify/)  
   Aspose.OCR provides detailed information about the characters found in the image and their possible alternatives.
2. [Defining the whitelist of characters.](/ocr/python-net/characters-whitelist/)  
   Limit the set of characters Aspose.OCR engine will look for.
3. [Defining the blacklist of characters.](/ocr/python-net/characters-blacklist/)  
   Explicitly ignore certain image defects that may be incorrectly recognized as characters.
