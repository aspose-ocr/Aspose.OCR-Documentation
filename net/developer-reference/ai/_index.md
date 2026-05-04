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
description: AI-powered OCR postprocessing with LLM/VLM models for smarter table output, text correction, and keyword extraction.
keywords:
- asposeai
- llm
- vlm
- model
- huggingface
- postprocessing
---

The `AsposeAI` class is a powerful bridge between OCR and modern AI models. It connects LLM/VLM inference with recognition output, turning raw OCR text into cleaner, smarter, and more actionable results.

### 🚀 Why this matters

- Improve table reconstruction and layout quality with [AI table correction](/ocr/net/ai/ai-table/).
- Fix OCR mistakes automatically with [AI spell-check correction](/ocr/net/ai/ai-spell-check/).
- Extract key phrases and numeric values with [AI keyword detection](/ocr/net/ai/ai-keywords/).
- Bring your own model from Hugging Face and tune runtime settings for your workload.

### 🛠 Constructors

```csharp
public AsposeAI();
public AsposeAI(ILogger logger);
```

You can also pass optional logging and customization callbacks.

### Configuration
### ⚙️ AsposeAIModelConfig

| Property                  | Type     | Description                                                                                                                                                    |
| ------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `AllowAutoDownload`       | `string` | If true, the model will be automatically downloaded if not available locally.                                                                                  |
| `DirectoryModelPath`      | `string` | Optional path where downloaded or processed models will be cached. If not set, a default system location will be used.                                         |
| `FileModelPath`           | `string` | Local path to the folder containing the model files. If specified, this will be used instead of downloading. Default empty.                                    |
| `HuggingFaceFileName`     | `string` | Optional model filename to download from Hugging Face (for example, `TableGPT2-7B.Q4_K_S.gguf`). Use it to pin an exact model artifact for reproducible results. |
| `HuggingFaceRepoId`       | `string` | Hugging Face repository ID (for example, `bartowski/Qwen2.5-3B-Instruct-GGUF`). Set this to bring your own model and adapt AI behavior to your domain. |
| `ContextSize`             | `int` | Maximum context window (tokens) for LLM/VLM inference. Increase it for harder documents and richer reasoning; reduce it to save memory. If null, the model default is used. |
| `GpuLayers`               | `int` | Number of model layers to run on GPU. Increase for faster inference on supported hardware, or set to `0` for CPU-only execution. Default: `40`. |

### 🧠 AsposeAI Class – Core Methods
| Method                                                                        | Description                                                         |
| ----------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `SetPostProcessor(IOcrAIPostProcessor processor, AsposeAIModelConfig config)` | Adds a custom AI postprocessor to enhance OCR results.              |
| `RunPostprocessor(List<string> texts)`                                        | Enhances plain recognized text strings using registered AI modules. |
| `RunPostprocessor(OcrOutput output)`                                          | Enhances structured OCR output using registered AI modules.         |
| `Dispose()`                                                                   | Cleans up and releases resources used by the AI component.          |
| `FreeResources()`                                                             | Explicitly unloads AI models and clears memory.                     |
| `ListLocal()`                                                                 | Lists all local AI models available in the configured folder.       |
| `GetLocalPath()`                                                              | Returns the directory path of the current model location.           |
| `IsInitialized()`                                                             | Checks if the AI engine and model are ready to use.                 |
