---
weight: 69
date: "2025-08-30"
author: "Anna Pylaieva"
type: docs
url: /net/ai/ai-table
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
title: AsposeAI Table correction
description: Improve OCR accuracy by applying LLM‑powered table layout output.
keywords:
- asposeai
- llm
- table
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

The `AsposeAI` class integrates external AI models (e.g., from Hugging Face) into OCR recognition results for **table layout correction** and intelligent postprocessing.

## Constructor

```csharp
public AsposeAI();
public AsposeAI(ILogger? logger);
```

You can also pass optional logging and customization callbacks.

### 🔤 TableAIProcessor Class – Postprocessor Module

- Implements: `IOcrAIPostProcessor`
- Description: A built-in module that performs AI-powered table detection and layout correction.
- Usage: Register using `AsposeAI.SetPostProcessor(new SpellCheckAIProcessor())`

## 🔗 API References

- [`AsposeAI`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeai/)  
  Core class to load, configure, and apply AI models (e.g., for table correction) to OCR results.

- [`TableAIProcessor`](https://reference.aspose.com/ocr/net/aspose.ocr.ai/tableaiprocessor/)  
  Built-in AI postprocessor that uses a language model to improve table layout detection and formatting.


```csharp
   ILogger logger = new ConsoleLogger(); // can be null
   AsposeAIModelConfig modelConfig = new AsposeAIModelConfig
   {
       AllowAutoDownload = true,
       DirectoryModelPath = "D://test",
   };

   AsposeAI ai = new AsposeAI(logger);
   TableAIProcessor processor = new TableAIProcessor()
   ai.SetPostProcessor(processor, modelConfig);
   ai.RunPostprocessor(res, AITableDetectionMode.AUTO);

   Console.WriteLine("CORRECTED RESULT\n");
   Console.WriteLine(processor.GetResult()[0].RecognitionText)
   ai.Dispose();
```

## Live demo

<div class="duo">
<img src="table2.jpg" alt="AI spell-check" />
<pre class="rec-result">
Table 2. Result of Polarity of Twitter Dataset
Trend Name Positive Sentiments Negative Sentiments Neutral Sentiments Tweets used
#GST4India 2427 123 2450 5000
#startupindia 924 192 1384 2500
#SwachBharat 1983 409 2138 4530
#FinBudget 7791 4662 12547 25000
#Digital india 1238 411 3351 5000
#RailwayBudget 1257 618 2115 4000
#MakeInIndia 3383 454 6163 10000
#Kashmir 923 1399 1678 4000
International Conference On Recent Advances In Computer Science, Engineering And Technology 75|Page
</pre>
<pre class="ai-result">
| Trend Name | Positive Sentiments | Negative Sentiments | Neutral Sentiments | Tweets used |
| --- | --- | --- | --- | --- |
| #GST4India | 2427 | 123 | 2450 | 5000 |
| #startupindia | 924 | 192 | 1384 | 2500 |
| #SwachBharat | 1983 | 409 | 2138 | 4530 |
| #FinBudget | 7791 | 4662 | 12547 | 25000 |
| #Digital india | 1238 | 411 | 3351 | 5000 |
| #RailwayBudget | 1257 | 618 | 2115 | 4000 |
| #MakeInIndia | 3383 | 454 | 6163 | 10000 |
| #Kashmir | 923 | 1399 | 1678 | 4000 |
</pre>
</div>

<button onclick="$('.rec-result').slideDown(100); $('.ai-result').slideUp(100);">Extract text</button>
<button onclick="$('.ai-result').slideDown(100)">AI table extract</button>

### 🐞 Logging & error handling
Pass `ILogger` to constructor to track loading and inference.
