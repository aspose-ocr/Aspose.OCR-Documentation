---
weight: 70
date: "2025-07-10"
author: "Anna Pylaieva"
type: docs
url: /net/ai/ai-spell-check
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
title: AsposeAI Spell-check correction
description: Improve OCR accuracy by applying LLM‑powered spell‑check to raw output.
keywords:
- asposeai
- llm
- spell-check
- model
- huggingface
---

<style>
	button {
		cursor: pointer;
		margin-right: 20px;
		margin-bottom: 20px;
		padding: 7px 15px;
		border: none;
		border-radius: 5px;
		background-color: #1a89d0;
		font-weight: 700;
		font-size: 15px;
		color: #ffffff;
	}

	button:hover {
		background-color: #3071a9;
	}

	button:focus {
		outline: none;
	}

	.duo {
		display: flex;
		flex-direction: row;
		align-items: stretch;
		margin-bottom: 20px;
	}

	.duo > * {
		margin-bottom: 0 !important;
	}

	.duo > pre {
		display: none;
		margin-left: 15px;
		min-width: 300px;
	}
</style>

The `AsposeAI` class integrates external AI models (e.g., from Hugging Face) into OCR recognition results for **spell-check correction** and intelligent postprocessing.

## Constructor

```csharp
public AsposeAI();
public AsposeAI(AsposeAIModelConfig config, ILogger? logger = null);
```

You can also pass optional logging and customization callbacks.

### 🔤 SpellCheckAIProcessor Class – Postprocessor Module

- Implements: `IOcrAIPostProcessor`
- Description: A built-in module that performs AI-powered spell-check correction.
- Usage: Register using `AsposeAI.AddPostProcessor(new SpellCheckAIProcessor())`

## 🔗 API References

- [`AsposeAI`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeai/)  
  Core class to load, configure, and apply AI models (e.g., for spell correction) to OCR results.

- [`SpellCheckAIProcessor`](https://reference.aspose.com/ocr/net/aspose.ocr.ai/spellcheckaiprocessor/)  
  Built-in AI postprocessor that uses a language model to fix spelling mistakes in recognized text.


```csharp
   ILogger logger = new ConsoleLogger(); // can be null
   AsposeAIModelConfig modelConfig = new AsposeAIModelConfig
   {
       AllowAutoDownload = true,
       DirectoryModelPath = "D://test",
   };

   AsposeAI ai = new AsposeAI(modelConfig, logger);

   ai.AddPostProcessor(new SpellCheckAIProcessor());
   ai.RunPostprocessor(res);

   Console.WriteLine("CORRECTED RESULT\n");
   Console.WriteLine(res[0].RecognitionText)
   ai.Dispose();
```

## Live demo

<div class="duo">
<img src="demo.jpg" alt="AI spell-check" />
<pre class="rec-result">
 POWER SUPPLY
 THE CALCULATOR IS POWERED BY
 SOLAR CELL AND A BATTERY FOR
 BACKUP.THE DIS LAY WILL DIM WHEN
 THE BATERY NEEDSTO BEREPLACED
 THE"+"SIGN OF EACH BATTERY MUST
 SHOW UPWARD WHEN INSERTEDI
</pre>
<pre class="ai-result">
 POWER SUPPLY
THE CALCULATOR IS POWERED BY
SOLAR CELL AND A BATTERY FOR
BACKUP THE DISPLAY WILL DIM WHEN
THE BATTERY NEEDS TO BE REPLACED
THE"+"SIGN OF EACH BATTERY MUST
SHOW UPRIGHT WHEN INSERTED
</pre>
</div>
<button onclick="$('.duo > pre').slideDown(100)">Extract text</button>
<button onclick="$('.duo > ai-result').slideDown(100)">AI spell-check</button>

### 🐞 Logging & error handling
Pass `ILogger` to constructor to track loading and inference.
