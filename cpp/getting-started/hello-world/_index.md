---
weight: 50
date: "2022-12-07"
author: "Vladimir Lapin"
type: docs
url: /cpp/hello-world/
feedback: OCRCPP
title: Hello, world!
description: Get started with Aspose.OCR for C++ by creating and running a bare minimum example.
keywords:
- hello world
- evaluation
- example
- sample
- dummies
- code
---

In this article, you will learn how to build a bare minimum console application for extracting text from an image with with Aspose.OCR for C++.

{{% alert color="primary" %}} 
We assume that you already have a basic knowledge of **Microsoft Visual Studio** and **C++**.
{{% /alert %}} 

## You will need

- A [compatible](/ocr/cpp/system-requirements/) system with Microsoft Visual Studio installed. As an individual developer, you can use a free Visual Studio Community Edition.
- Some image containing a text. You can simply download the one from the article.
- **5 minutes** of spare time.

## Preparing

1. Create a new C++ project in Visual Studio. You can use a very basic project template, such as **Console App**.
2. [Install](/ocr/cpp/installation/) **Aspose.OCR.Cpp** (CPU-based) NuGet package to the project.
3. Save this image to **x64\\Debug** directory of the project under the name `source.png`:  
   <img src="source.png" alt="Source image" style="box-shadow: 1px 1px 4px 2px rgba(0,0,0,0.2);margin-top:8px;" />  

   If this folder does not exist, run the application.

## Coding

1. Include the required header files to the project:
   ```cpp
   #include <iostream>
   #include <stdio.h>
   #include <fcntl.h>
   #include <io.h>
   #include <aspose_ocr.h>
   ```
2. Provide the recognized image by file path:
   ```cpp
   string file = "source.png";
   AsposeOCRInput source;
   source.url = file.c_str();
   std::vector<AsposeOCRInput> content = { source };
   ```
3. Specify the recognition language
   ```cpp
   RecognitionSettings settings;
   settings.language_alphabet = language::eng;
   ```
4. Extract text from the image:
   ```cpp
   auto result = asposeocr_recognize(content.data(), content.size(), settings);
   ```
5. Output the recognized text:
   ```cpp
   wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
   std::cout << std::wstring(buffer) << std::endl;
   ```
6. Release the resources
   ```cpp
   asposeocr_free_result(result);
   ```


## Full code

```cpp
#include <iostream>
#include <stdio.h>
#include <fcntl.h>
#include <io.h>
#include <aspose_ocr.h>

int main()
{
	// Set output console mode
	_setmode(_fileno(stdout), _O_U16TEXT);
	// Provide the image
	string file = "source.png";
	AsposeOCRInput source;
	source.url = file.c_str();
	std::vector<AsposeOCRInput> content = { source };
	// Set recognition language
	RecognitionSettings settings;
	settings.language_alphabet = language::eng;
	// Extract text from the image
	auto result = asposeocr_recognize(content.data(), content.size(), settings);
	// Output the recognized text
	wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
	std::cout << std::wstring(buffer) << std::endl;
	// Release the resources
	asposeocr_free_result(result);
}
```

## Running

Run the program. You will see extracted text in the console output:

```
Hello, World! I can read this text.
```

{{% alert color="primary" %}} 
If you use your own image, consider the [trial restrictions](/ocr/cpp/licensing/).
{{% /alert %}} 

## What's next

Congratulations! You have extracted the text from the image. Read the [Developer reference](/ocr/cpp/developer-reference/) and [API reference](https://reference.aspose.com/ocr/cpp/) for details on developing advanced applications with Aspose.OCR for C++.
