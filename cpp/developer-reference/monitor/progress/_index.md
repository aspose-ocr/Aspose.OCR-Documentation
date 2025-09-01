---
weight: 10
date: "2023-07-20"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /cpp/track-progress/
feedback: OCRCPP
title: Tracking recognition progress
description: How to track the process of recognition and text extraction from multipage documents.
keywords:
- process
- batch
- pages
- progress
- event
---

Aspose.OCR for C++ allows you to implement an event listener and report recognition progress using [`asposeocr_set_progress_tracker()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga873f140926ea65a2a74f4dae58af7961) function.

For each page or file, the following information is reported:

Property | Description
-------- | -----------
`images_amount` | The total number of source images to be recognized.
`current_image_number` | The ordinal number of the image.
`current_state` | The **stage** of the recognition progress.

## Recognition progress stages

Stage | Description
----- | -----------
`ASPOSE_OCR_START` | Recognition started.
`ASPOSE_OCR_LOADED` | The [image](/ocr/cpp/content-for-ocr/) was sent for recognition.
`ASPOSE_OCR_PREPROCESSED` | The image was processed through [preprocessing filters](/ocr/cpp/image-preprocessing/).
`ASPOSE_OCR_REGIONS_DETECTED` | The image is split into [content blocks](/ocr/cpp/areas-detection/).
`ASPOSE_OCR_TEXT_RECOGNIZED` | Recognition finished.

## Example

```cpp
void progress_tracker(const AsposeOCRProgress& input)
{
	std::cout << "Number of images: " << input.images_amount
		<< " current image: " << input.current_image_number
		<< " current state: " << input.current_state << std::endl;
}

<...>

asposeocr_set_progress_tracker(&progress_tracker);
```
