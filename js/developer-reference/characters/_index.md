---
weight: 30
date: "2023-12-04"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/characters/
feedback: OCRCPP
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

Aspose.OCR for JavaScript via C++ supports a [large list](/ocr/javascript-cpp/recognition-languages/) of extended Latin, Cyrillic, and Asian characters. However, a typical image contains no more than half of these characters. You can greatly improve the accuracy and performance of recognition by specifying which characters the OCR engine will look for.

The full workflow is as follows:

1. [Defining the whitelist of characters.](/ocr/javascript-cpp/characters-whitelist/)  
   Limit the set of characters Aspose.OCR engine will look for.
2. [Defining the blacklist of characters.](/ocr/javascript-cpp/characters-blacklist/)  
   Explicitly ignore certain image defects that may be incorrectly recognized as characters.
