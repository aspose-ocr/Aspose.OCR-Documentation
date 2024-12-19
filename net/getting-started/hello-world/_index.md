---
weight: 50
date: "2024-12-18"
author: "Vladimir Lapin"
type: docs
url: /net/hello-world/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
title: Hello, world!
description: Get started with Aspose.OCR for .NET by creating and running a bare minimum example.
keywords:
- hello world
- evaluation
- example
- sample
- dummies
- code
---

In this article, you will learn how to build a bare minimum console application for extracting text from an image with with Aspose.OCR for .NET.

{{% alert color="primary" %}} 
We assume that you already have a basic knowledge of **Microsoft Visual Studio** and **C#**.
{{% /alert %}} 

## You will need

- A [compatible](/ocr/net/system-requirements/) system with Microsoft Visual Studio installed. As an individual developer, you can use a free Visual Studio Community Edition.
- Some image containing a text. You can simply download the one from the article.
- **5 minutes** of spare time.

## Preparing

1. Create a new C# project in Visual Studio. You can use a very basic project template, such as **Console App**.
2. [Install](/ocr/net/installation/) **Aspose.OCR** (CPU-based) NuGet package to the project.
3. Save this image to **bin\\Debug** or **bin\\Debug\\net6.0** directory of the project under the name `source.png`:  
   <img src="source.png" alt="Source image" style="box-shadow: 1px 1px 4px 2px rgba(0,0,0,0.2);margin-top:8px;" />

## Coding

1. Create an instance of Aspose.OCR recognition engine:
   ```csharp
   Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
   ```
2. Add the image to `OcrInput` object:
   ```csharp
   Aspose.OCR.OcrInput source = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
   source.Add("source.png");
   ```
3. Extract text from the image:
   ```csharp
   Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(source);
   ```
3. Output the recognized text:
   ```csharp
   Console.WriteLine(results[0].RecognitionText);
   ```

Full code:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.OcrInput source = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
source.Add("source.png");
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(source);
Console.WriteLine(results[0].RecognitionText);
```

## Running

Run the program. You will see extracted text in the console output:

```
Hello, World! I can read this text.
```

{{% alert color="primary" %}} 
If you use your own image, consider the [trial restrictions](/ocr/net/licensing/).
{{% /alert %}} 

## What's next

Congratulations! You have extracted the text from the image. Read the [Developer reference](/ocr/net/developer-reference/) and [API reference](https://reference.aspose.com/ocr/net/) for details on developing advanced applications with Aspose.OCR for .NET.

