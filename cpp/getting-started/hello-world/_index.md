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
2. Provide the path to the recognized image:
   ```cpp
   std::string image_path = "source.png";
   ```
3. Prepare the buffer for recognition results (in characters):
   ```cpp
   const size_t len = 4096;
   wchar_t buffer[len] = { 0 };
   ```
4. Extract text from the image:
   ```cpp
   size_t size = aspose::ocr::page(image_path.c_str(), buffer, len);
   ```
5. Output the recognized text:
   ```cpp
   std::wcout << buffer << L"\n";
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
	// Provide the path to the recognized image
	std::string image_path = "source.png";
	// Prepare the buffer for recognition results
	const size_t len = 4096;
	wchar_t buffer[len] = { 0 };
	// Extract text from the image
	size_t size = aspose::ocr::page(image_path.c_str(), buffer, len);
	// Print result
	std::wcout << buffer << L"\n";
	// Exit the program
	std::wcout << "\nRecognition complete. Press any key to exit...";
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
