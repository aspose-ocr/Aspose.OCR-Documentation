---
weight: 50
date: "2025-02-28"
author: "Vladimir Lapin"
type: docs
url: /net/onnx_options/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
title: Overriding ONNX options
description: How to override the default ONNX runtime settings.
keywords:
- ONNX
- backend
- library
- engine
---

Aspose.OCR for .NET leverages ONNX Runtime as its machine learning engine. While its communication with ONNX Runtime is optimized for the majority of common environments, the library's behavior can be fine-tuned for specific hardware.

{{% alert color="caution" %}} 
Unless you are absolutely sure, we recommend keeping the default ONNX settings. Providing custom values may lead to significant performance degradation or stability issues.
{{% /alert %}}

ONNX runtime is configured through `Aspose.OCR.OnnxRuntimeSessionOptions` static class. This class exposes the following properties:

Property | Type | Description
-------- | -----| -----------
`GraphOptimizationLevel` | `Aspose.OCR.GraphOptimizationLevelOnnx` | Graph optimization level for the session:<ul><li>`ORT_DISABLE_ALL` - disable all optimizations.</li><li>`ORT_ENABLE_BASIC` - enable basic optimizations, such as node fusion and constant folding.</li><li>`ORT_ENABLE_EXTENDED` - enable extended optimizations, including memory layout improvements.</li><li>`ORT_ENABLE_ALL` - enable all available optimizations for maximum performance.</li></ul>By default, all available optimizations are enabled.
`ExecutionMode` | `Aspose.OCR.ExecutionModeOnnx` | Execution mode for the session:<ul><li>`ORT_SEQUENTIAL` - execute operators sequentially, ensuring that each operation is completed before the next one starts.</li><li>`ORT_PARALLEL` - execute operators in parallel (whenever possible), to improve performance.</li></ul>By default, operators are executed concurrently, whenever possible.
`IntraOpNumThreads` | `int` | Number of threads for a single operations.
`InterOpNumThreads` | `int` | Number of threads for running multiple operations in parallel. If sequential execution (`ExecutionModeOnnx.ORT_SEQUENTIAL`) is enabled in `ExecutionMode` property, this value is ignored.

For technical details, refer to [ONNX Runtime documentation](https://onnxruntime.ai/docs).

{{% alert color="primary" %}} 
If you decide to override the default ONNX runtime settings, perform it before calling any other recognition method.
{{% /alert %}}

## Example

Changing the number of threads for ONNX runtime:

```csharp
Aspose.OCR.OnnxRuntimeSessionOptions.IntraOpNumThreads = 8;
// Initialize recognition API
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source1.png");
input.Add("source2.jpg");
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input);
```
