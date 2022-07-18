---
title: Provide ignored characters during OCR operation
type: docs
weight: 60
url: /cpp/provide-ignored-characters-during-ocr-operation/
---

## **Provide ignored characters during OCR operation**
In case you know the characters that aren't present in the image, you can pass those characters as a value for property 
[**RecognitionSettings.ignoredCharacters **](https://reference.aspose.com/ocr/cpp/struct/recognition_settings#a7208bc782b0310a20c2671749c61fbc9). 
Doing this will ensure that the provided characters aren't matched in the OCR process. The following code snippet demonstrates setting the ignored characters for the OCR process.

## Sample Code

```cpp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-C
	const char* uri = "https://assets.htmlacademy.ru/content/blog/94/text-bottom-1@1x.png";
    const size_t len = 4096;
    wchar_t buffer[len] = { 0 };

    RecognitionSettings settings;
    settings.ignoredCharacters = L"abc";
    size_t res = aspose::ocr::page_from_uri(uri, buffer, len, settings);

    std::wcout << buffer;
```

