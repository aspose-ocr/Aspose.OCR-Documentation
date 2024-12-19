---
weight: 20
date: "2024-12-18"
author: "Vladimir Lapin"
type: docs
url: /net/save-text/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
title: Getting recognition results as text
description: Returning Aspose.OCR for .NET recognition results as formatted text.
keywords:
- save
- result
- text
- txt
- output
---

Recognition results in plain text with line breaks can be obtained from the [`RecognitionText`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/recognitiontext/) property of [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object or returned from [`RecognizeImage`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizeimage/#recognizeimage_6) method.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input);
// Show recognition result
Console.WriteLine(result[0].RecognitionText);
```

You can also extract text blocks from [specific image areas](/ocr/net/image-regions-extract/) or get [individual lines](/ocr/net/image-line-extract/).
