---
weight: 70
date: "2025-09-14"
author: "Anna Pylaieva"
type: docs
url: /python-net/ai/
feedback: OCRPYNET
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

```python
AsposeAI()
AsposeAI(logging)
```

You can also pass optional logging and customization callbacks.

### Configuration
### ⚙️ AsposeAIModelConfig

| Property                   | Type     | Description                                                                                                                                                    |
| -------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `allow_auto_download`      | `string` | If true, the model will be automatically downloaded if not available locally.                                                                                  |
| `directory_model_path`     | `string` | Optional path where downloaded or processed models will be cached. If not set, a default system location will be used.                                         |
| `file_model_path`          | `string` | Local path to the folder containing the model files. If specified, this will be used instead of downloading. Default empty.                                    |
| `hugging_face_quantization`| `string` | Optional quantization type to use when downloading from HuggingFace. Examples: “int8”, “fp16”, “none”. Default q4_k_m.                                         |
| `hugging_face_repo_id`     | `string` | ID of the model on HuggingFace (e.g., “openai/gpt2”). If specified, the model will be downloaded from HuggingFace. Default bartowski/Qwen2.5-3B-Instruct-GGUF. |
| `context_size`             | `int`    | 	Defines the maximum number of tokens the LLM can use as context during inference. If null, the default context size defined by the model will be used. Larger values allow the model to consider more text but may require more memory. |
| `gpu_layers`               | `int`    | Number of GPU layers to use for the model. If not specified, the default value (40) will be used. Set to 0 to run entirely on the CPU. |

### 🧠 AsposeAI Class – Core Methods
| Method                                            | Description                                                         |
| ------------------------------------------------- | ------------------------------------------------------------------- |
| `set_post_processor(processor, custom_settings)`  | Adds a custom AI postprocessor to enhance OCR results.              |
| `run_postprocessor(res)`                          | Enhances plain recognized text strings using registered AI modules. |
| `run_postprocessor(res)`                          | Enhances structured OCR output using registered AI modules.         |
| `free_resources()`                                | Explicitly unloads AI models and clears memory.                     |
| `list_local()`                                    | Lists all local AI models available in the configured folder.       |
| `get_local_path()`                                | Returns the directory path of the current model location.           |
| `is_initialized()`                                | Checks if the AI engine and model are ready to use.                 |
