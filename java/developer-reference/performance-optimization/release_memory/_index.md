---
weight: 40
date: "2024-12-16"
author: "Vladimir Lapin"
type: docs
url: /java/release_memory/
feedback: OCRJAVA
title: Unloading OCR modules from memory
description: Release memory occupied by Aspose.OCR for Java recognition engine by unloading unneeded OCR modules.
keywords:
- ram
- memory
- garbage
- release
- free
---

Aspose.OCR for Java allows you to manually release the memory occupied by the recognition engine by unloading unused [OCR features](/ocr/java/modules/). This can significantly optimize resource usage, which is especially useful in web applications and microservices.

To unload OCR modules from memory, call `Resources.ReleaseMemory()` method.

{{% alert color="primary" %}}
This method will only affect the modules currently loaded into RAM. The downloaded module files will remain stored on your system. This ensures that the modules can be reloaded quickly if needed, without requiring additional downloads.
{{% /alert %}}

If you need to use the OCR module again later, it will automatically reload into memory when you perform recognition that requires module-specific features. This ensures that the necessary components are always available for accurate processing. However, please note that the first recognition attempt after reloading may be slightly slower due to the initialization process.

## Example

```java
// Download Hindi OCR model to "aspose/ocr" directory in the application working directory
Resources.SetLocalPath("aspose/ocr");
Resources.FetchResource("aspose-ocr-hindi-v1");
// Initialize Aspose.OCR recognition API
AsposeOCR api = new AsposeOCR();
RecognitionSettings recognitionSettings = new RecognitionSettings();
// Add image to the recognition batch
OcrInput source = new OcrInput(InputType.SingleImage);
source.add("image.png");
// Extract text from image
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setLanguage(Language.Hin);
ArrayList<RecognitionResult> results = api.Recognize(source, recognitionSettings);
System.out.println(result[0].recognition_text);
// Unload all OCR models from memory to free up resources
Resources.ReleaseMemory();
```
