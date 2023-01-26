---
weight: 20
date: "2022-09-06"
author: "Vladimir Lapin"
type: docs
url: /net/save-text/
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

{{< tabs tabID="1" tabTotal="2" tabName1="RecognitionText property" tabName2="RecognizeImage method" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
string result = recognitionEngine.RecognizeImage("source.png");
Console.WriteLine(result);
```
{{< /tab >}}
{{< /tabs >}}

You can also extract text blocks from [specific image areas](/ocr/net/image-regions-extract/) or get [individual lines](/ocr/net/image-line-extract/).
