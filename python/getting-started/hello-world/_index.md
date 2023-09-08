---
weight: 40
date: "2023-04-19"
author: "Vladimir Lapin"
type: docs
url: /python-net/hello-world/
feedback: OCRPYNET
title: Hello, world!
description: Get started with Aspose.OCR for Python via .NET by creating and running a bare minimum example.
keywords:
- hello world
- evaluation
- example
- sample
- dummies
- code
---

In this article, you will learn how to build a bare minimum Python console application for extracting text from an image with Aspose.OCR for Python via .NET.

{{% alert color="primary" %}} 
We assume that you already have a basic knowledge of how to write and run Python scripts.
{{% /alert %}} 

## You will need

- A [compatible](/ocr/python-net/system-requirements/) system with Python 3.6 or later installed. It is recommended to use the latest version of Python.
- Pip package installer.
- Any plain text editor.
- Some image containing a text. You can simply download the one from the article.
- **5 minutes** of spare time.

## Preparing the environment

1. [Install](/ocr/python-net/installation/) **Aspose.OCR for Python via .NET** package using pip.
2. Create a text file called `ocr.py`.
3. Save this image file to the same directory as **ocr.py** under the name **source.png**:  
   <img src="source.png" alt="Source image" style="box-shadow: 1px 1px 4px 2px rgba(0,0,0,0.2);margin-top:8px;" />

## Coding

Open **ocr.py** in whatever code or plain text editor you prefer.

1. Import **aspose.ocr** module:  
   ```python
   import aspose.ocr as ocr
   ```
2. Create an instance of Aspose.OCR API:
   ```python
   api = AsposeOcr()
   ```
3. Add the image to the recognition batch:
   ```python
   input = OcrInput(InputType.SINGLE_IMAGE)
   input.add("source.png")
   ```
4. Extract text from the image:
   ```python
   result = api.recognize(input)
   ```
5. Output the recognized text:
   ```python
   print(result[0].recognition_text)
   ```

Full code:

```python
import aspose.ocr as ocr

# Instantiate Aspose.OCR API
api = AsposeOcr()

# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")

# Recognize the image
result = api.recognize(input)

# Print recognition result
print(result[0].recognition_text)
input("Press Enter to continue...")
```

## Running

Run **ocr.py**. You will see extracted text in the console output:

```
Hello, World! I can read this text.
Press Enter to continue...
```

{{% alert color="primary" %}} 
If you use your own image, consider the [trial restrictions](/ocr/net/licensing/).
{{% /alert %}} 
