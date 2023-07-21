---
weight: 10
date: "2023-0-08"
author: "Vladimir Lapin"
type: docs
url: /cpp/characters-identify/
feedback: OCRCPP
aliases:
- /cpp/get-choices-for-recognized-characters/
- /cpp/advanced-operations/
title: Identifying the characters
description: Detecting the characters in an image.
keywords:
- symbols
- characters
- letters
- probability
- list
- detect
---

Aspose.OCR can automatically build a list of characters found in an image and provide less likely alternatives of each character (in descending order of probability). To get the list of characters, use [`asposeocr_page_characters_choices()`](https://reference.aspose.com/ocr/cpp/groupAspose#gabcfa78f3bd39ad8aaca88e8c5429e5f6) or [`asposeocr_page_characters_choices_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga1de63dc740d47c0f0ce4aa433da81606) functions.

{{< tabs tabID="1" tabTotal="2" tabName1="From image" tabName2="From bytes" >}}
{{< tab tabNum="1" >}}
```cpp
std::string image_path = "source.png";
// allocate memory for a recognized character and 5 alternatives
const size_t len = 4096;
wchar_t buffer[len][6] = { 0 };
RecognitionSettings settings;
size_t res_len = asposeocr_page_characters_choices(image_path.c_str(), buffer, len, settings);
for (size_t i = 0; i < res_len; i++)
{
	// output recognized character
	std::wcout << buffer[i][0] << " - choices: ";
	// all alternatives
	for (size_t j = 1; j < 5; j++)
	{
		std::wcout << buffer[i][j] << " ";
	}
	std::wcout << std::endl;
}
std::wcout << std::endl;
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```cpp
unsigned char*** img_raw = <...>;
ImageDescriptor descriptor;
descriptor.image_from_raw_bytes = img_raw;
descriptor.height = 2000;
descriptor.width = 800;
descriptor.channels_size = 3;
// allocate memory for a recognized character and 5 alternatives
const size_t len = 4096;
wchar_t buffer[len][6] = { 0 };
RecognitionSettings settings;
size_t res_len = asposeocr_page_characters_choices_from_raw_bytes(descriptor, buffer, len, settings);
for (size_t i = 0; i < res_len; i++)
{
	// output recognized character
	std::wcout << buffer[i][0] << " - choices: ";
	// all alternatives
	for (size_t j = 1; j < 5; j++)
	{
		std::wcout << buffer[i][j] << " ";
	}
	std::wcout << std::endl;
}
std::wcout << std::endl;
```
{{< /tab >}}
{{< /tabs >}}

The list of _unique characters_ can later be used for identifying a [whitelist](/ocr/cpp/characters-whitelist/) to greatly improve the accuracy and performance of recognition.

_Alternatives_ can be used to find out patterns in common recognition errors, such as misidentifying certain characters in a font used in an image, and to take corrective action, such as automatic substitution.
