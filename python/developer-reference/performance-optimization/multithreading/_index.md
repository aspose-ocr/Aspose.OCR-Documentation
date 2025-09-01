---
weight: 30
date: "2023-09-15"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/multithreading/
feedback: OCRPYNET
title: Multithreading support
description: Optimize the resource usage by limiting the number of threads used by Aspose.OCR for Python via .NET recognition engine.
keywords:
- thread
- cpu
- core
---

Aspose.OCR for Python via .NET allows you to limit the number of threads used by the recognition engine. Decreasing the number of threads may slow down the recognition speed, but will allow you to reserve some resources for other processes such as the parallel image processing or background data analysis.

{{% alert color="primary" %}}
Regardless of the setting, the number of threads cannot exceed the total number of CPU cores/threads.
{{% /alert %}}

To set the number of threads, use `threads_count` parameter of the [recognition settings](/ocr/python-net/settings/):

Value | Behavior
----- | --------
_Not set_ | The OCR engine will use all CPU cores/threads.
0 | The OCR engine will use all CPU cores/threads.
1 | OCR will be performed on the application's main thread.
_More than 1_ | The OCR engine will use the number of threads provided, but not more than the total number of CPU cores/threads. Read [How it works](#how-it-works) for technical details.

## How it works

Multithreading works differently depending on the number of images in the [recognition batch](/ocr/python-net/ocrinput/).

### Recognizing one image

Applies to:

- recognition of a single image;
- recognition of a single-page PDF.

Aspose.OCR for Python via .NET will use the provided number of threads to recognize blocks of text found on the image/page in parallel.


### Recognizing multiple files/pages

Applies to:

- recognition of several images;
- recognition of multi-page PDF documents;
- recognition of multi-page TIFF images;
- recognition of DjVu files;
- bulk recognition of all images in a folder;
- bulk recognition of all images in a ZIP archive.

Each image from the batch is processed in **one** separate thread. If more than one thread is specified in `threads_count` parameter, images are recognized in parallel. The number of images processed simultaneously cannot exceed the value of `threads_count` [recognition settings](/ocr/python-net/settings/) or the total number of CPU cores/threads (whichever is less). Image regions are always recognized one by one.

{{% alert color="info" %}}
Since each image in a batch is recognized in one thread, the maximum number of threads used by the Aspose.OCR engine will not exceed the total number of images regardless of the `threads_count` setting.
{{% /alert %}}

## Example

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add images to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source1.png")
input.add("source2.png")
input.add("source3.png")
input.add("source4.png")
# Limit resource usage to 2 threads
recognitionSettings = RecognitionSettings()
recognitionSettings.threads_count = 2
# Recognize the image
results = api.recognize(input, recognitionSettings)
# Print recognition results
for result in results:
	print(result.recognition_text)
```
