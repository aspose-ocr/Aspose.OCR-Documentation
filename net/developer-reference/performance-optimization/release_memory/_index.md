---
weight: 40
date: "2024-12-06"
author: "Vladimir Lapin"
type: docs
url: /net/release_memory/
feedback: OCRNET
title: Unloading OCR modules from memory
description: Release memory occupied by Aspose.OCR for .NET recognition engine by unloading unneeded OCR modules.
keywords:
- ram
- memory
- garbage
- release
- free
---

Aspose.OCR for .NET allows you to manually release the memory occupied by the recognition engine by unloading unused [OCR features](/ocr/net/modules/). This can significantly optimize resource usage, which is especially useful in web applications and microservices.

To unload OCR modules from memory, call `Aspose.OCR.Resources.ReleaseMemory()` method.

{{% alert color="primary" %}}
This method will only affect the modules currently loaded into RAM. The downloaded module files will remain stored on your system. This ensures that the modules can be reloaded quickly if needed, without requiring additional downloads.
{{% /alert %}}

If you need to use the OCR module again later, it will automatically reload into memory when you perform recognition that requires module-specific features. This ensures that the necessary components are always available for accurate processing. However, please note that the first recognition attempt after reloading may be slightly slower due to the initialization process.

## Example

```csharp
// Download Chinese/English OCR model to "aspose/ocr" directory in the application working directory
Aspose.OCR.Resources.SetLocalPath("aspose/ocr");
Aspose.OCR.Resources.FetchResource("aspose-ocr-chinese-v2");
// Initialize Aspose.OCR for .NET recognition API
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source1.png");
input.Add("source2.jpg");
// Set recognition language (Chinese model is loaded to RAM)
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Chinese;
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
    Console.WriteLine(result.RecognitionText);
}
// Unload all OCR models from memory to free up resources
Aspose.OCR.Resources.ReleaseMemory();
```
