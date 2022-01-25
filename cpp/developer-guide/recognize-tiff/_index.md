---
title: Recognize multipage TIFF
type: docs
weight: 31
url: /cpp/recognize-multipage-tiff/
aliases:
    - /cpp/recognize-multipage-tiff/
---

## Recognize multipage TIFF

Aspose.OCR provides the [**aspose::ocr::page_tiff()**](https://apireference.aspose.com/ocr/cpp/groupAspose#ga674b2d618113a5a244f4289acfd8f48e) method that can recognize text on the images extracted from TIFF files. 
The [**aspose::ocr::page_tiff()**](https://apireference.aspose.com/ocr/cpp/groupAspose#ga674b2d618113a5a244f4289acfd8f48e) method 
takes the TIFF path as a parameter and RecognitionSettings object. 
The following code snippet demonstrates the use of the [**aspose::ocr::page_tiff()**](https://apireference.aspose.com/ocr/cpp/groupAspose#ga674b2d618113a5a244f4289acfd8f48e) method 
to recognize images from multipage TIFF(TIF) file.

# Sample Code 

```csharp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the TIFF file
	const size_t len = 4096;
    wchar_t buffer[len] = { 0 };

    RecognitionSettings set;
    size_t res_len = aspose::ocr::page_tiff("1.tif;2.tif", buffer, len, set);
	#ifdef _WIN32
		setmode(_fileno(stdout), 0x00020000);
	#else
		setlocale(LC_CTYPE, "");
	#endif
		std::wcout << buffer;
		
	res_len = aspose::ocr::page_tiff("1.tif", buffer, len, set);
```

