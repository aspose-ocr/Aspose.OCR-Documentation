---
weight: 70
date: "2025-07-10"
author: "Anna Pylaieva"
type: docs
url: /net/ai/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
title: AsposeAI class
description: Reference guide for the AsposeAI class for enabling spell-check correction using LLM models.
keywords:
- asposeai
- llm
- model
- huggingface
---

The `AsposeAI` class provides the bridge between LLM models and the OCR engine.

### 🛠 Constructors

```csharp
public AsposeAI();
public AsposeAI(AsposeAIModelConfig config, ILogger? logger = null);
```

You can also pass optional logging and customization callbacks.

### Configuration
### ⚙️ AsposeAIModelConfig

| Property                  | Type     | Description                                                                                                                                                    |
| ------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `AllowAutoDownload`       | `string` | If true, the model will be automatically downloaded if not available locally.                                                                                  |
| `DirectoryModelPath`      | `string` | Optional path where downloaded or processed models will be cached. If not set, a default system location will be used.                                         |
| `FileModelPath`           | `string` | Local path to the folder containing the model files. If specified, this will be used instead of downloading. Default empty.                                    |
| `HuggingFaceQuantization` | `string` | Optional quantization type to use when downloading from HuggingFace. Examples: “int8”, “fp16”, “none”. Default q4_k_m.                                         |
| `HuggingFaceRepoId`       | `string` | ID of the model on HuggingFace (e.g., “openai/gpt2”). If specified, the model will be downloaded from HuggingFace. Default bartowski/Qwen2.5-3B-Instruct-GGUF. |

### 🧠 AsposeAI Class – Core Methods
| Method                                            | Description                                                         |
| ------------------------------------------------- | ------------------------------------------------------------------- |
| `AddPostProcessor(IOcrAIPostProcessor processor)` | Adds a custom AI postprocessor to enhance OCR results.              |
| `CorrectResult(OcrOutput output)`                 | Applies AI-based spell correction to the full OCR result.           |
| `CorrectResult(RecognitionResult result)`         | Applies spell correction to a single recognition result.            |
| `RunPostprocessor(List<string> texts)`            | Enhances plain recognized text strings using registered AI modules. |
| `RunPostprocessor(OcrOutput output)`              | Enhances structured OCR output using registered AI modules.         |
| `Dispose()`                                       | Cleans up and releases resources used by the AI component.          |
| `FreeResources()`                                 | Explicitly unloads AI models and clears memory.                     |
| `ListLocal()`                                     | Lists all local AI models available in the configured folder.       |
| `GetLocalPath()`                                  | Returns the directory path of the current model location.           |
| `IsInitialized()`                                 | Checks if the AI engine and model are ready to use.                 |
