---
title: Get the set of characters with the alternatives
type: docs
weight: 30
url: /cpp/get-choices-for-recognized-characters/
description: This article explains how to get image recognition characters and choices to replace them with Aspose.OCR C++.
---

## Recognize Text on Image with Characters Choices

Aspose.OCR C++ provides a set of characters found by the recognition algorithm and arranged in descending order of probability. The following code shows how to get the array of symbols char[][6] with the maximum probability and alternatives using C++:


```cpp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-C
void GetChoicesForEachCharacterInResult() {
	std::string image_path = "../Data/Source/sample.png";

	// allocate memory for 5 characters choices +1 on '\0'
	const size_t len = 4096; // estimated  length of the text on the image
	wchar_t buffer[len][6] = { 0 };

	RecognitionSettings settings; // default
	size_t res_len = aspose::ocr::page_characters_choices(image_path.c_str(), buffer, len, settings);
	// res_len - the real length of the text on the image
	for (size_t i = 0; i < res_len; i++)
	{
		// print recognized letter
		std::wcout << buffer[i][0] << " - choices: ";
		// or print all cases std::wcout << buffer[i];
		for (size_t j = 1; j < 5; j++)
		{
			std::wcout << buffer[i][j] << " ";
		}
		std::wcout << std::endl;
	}

	std::wcout << std::endl;
}
```
