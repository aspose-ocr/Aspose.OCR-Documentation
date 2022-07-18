---
title: Save ocr result as multipage document
type: docs
weight: 30
url: /cpp/save-ocr-result-as-multipage-document/
---

## Recognize a list of images and save Searchable PDF (or DOCX)

Aspose.OCR for C++ can recognize a list of images. 

The [**page_save()**](https://reference.aspose.com/ocr/cpp/groupAspose#ga248e71b77ac6dbaf0c80630b2181cf29) method 
takes the input paths, output path as a parameter, file format(file_format) in RecognitionSettings structure. 

# Sample Code 

```cpp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-C
		const size_t len = 4096;
		wchar_t buffer[len] = { 0 };
		RecognitionSettings settings;
		settings.save_format = file_format::pdf;

		asposeocr_page_save("1.png;2.jpg;3.jpg", "result.pdf", settings);
```