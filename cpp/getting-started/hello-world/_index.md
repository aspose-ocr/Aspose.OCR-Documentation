---
weight: 50
date: "2023-08-29"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
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
2. [Install](/ocr/cpp/installation/) **Aspose.OCR.Cpp** (CPU-based) NuGet package to the project. This may take up to several minutes depending on your internet connection.
3. Download this sample image somewhere to your computer under the name `source.png`:  
   <img src="source.png" alt="Source image" style="box-shadow: 1px 1px 4px 2px rgba(0,0,0,0.2);margin-top:8px;" />  

   {{% alert color="info" %}} 
   For simplicity, this example assumes that the recognized image is located in the application's working directory. It depends on how you run the application:

   - **Project directory**, if you run the application directly from Visual Studio (Local Windows Debugger). 
   - **x64\\Debug** subfolder in the project directory if you plan to run the compiled application. If this folder does not exist, run the application first.
   {{% /alert %}} 

## Coding

1. Include the required header files to the project:
   ```cpp
   #include <iostream>
   #include <string>
   #include <vector>
   #include <aspose_ocr.h>
   ```

2. Declare the following statement to use names for objects and variables from the standard library without mentioning `std::` every time:
   ```cpp
   using namespace std;
   ```

   {{% alert color="info" %}} 
   The statement `using namespace std` is generally considered bad practice. In this basic example, it is only used to improve the readability of the code.

   When developing production applications, specify the namespace to which the identifier belongs using the scope operator(::) each time you declare a type. 
   {{% /alert %}} 

3. Provide the recognized image by file path:
   ```cpp
   string file = "source.png";
   AsposeOCRInput source;
   source.url = file.c_str();
   vector<AsposeOCRInput> content = {source};
   ```

   {{% alert color="info" %}} 
   The image file will be searched in the application's working directory (see the note in [Preparing](#preparing) section).

   Alternatively, you can specify the full image path (for example, `string file = "C:\\source.png";`) or calculate it in the runtime.
   {{% /alert %}} 

4. Specify the recognition language
   ```cpp
   RecognitionSettings settings;
   settings.language_alphabet = language::eng;
   ```

5. Extract text from the image:
   ```cpp
   AsposeOCRRecognitionResult result = asposeocr_recognize(content.data(), content.size(), settings);
   ```

6. Output the recognized text:
   ```cpp
   size_t size = 0;
   wchar_t* buffer = asposeocr_serialize_result(result, size);
   wcout << wstring(buffer) << endl;
   ```

7. Release the resources
   ```cpp
   asposeocr_free_result(result);
   ```


## Full code

```cpp
#include <iostream>
#include <string>
#include <vector>
#include <aspose_ocr.h>

using namespace std;

int main()
{
	// Provide the image  for recognition
	string file = "source.png";
	AsposeOCRInput source;
	source.url = file.c_str();
	vector<AsposeOCRInput> content = {source};
	// Set recognition language
	RecognitionSettings settings;
	settings.language_alphabet = language::eng;
	// Extract text from the image
	AsposeOCRRecognitionResult result = asposeocr_recognize(content.data(), content.size(), settings);
	// Output the recognized text
	size_t size = 0;
	wchar_t* buffer = asposeocr_serialize_result(result, size);
	wcout << wstring(buffer) << endl;
	// Release the resources
	asposeocr_free_result(result);
}
```

## Running

Run the program. You will see extracted text in the console output:

```
Hello. World! I can read this text
```

{{% alert color="primary" %}} 
If you use your own image, consider the [trial restrictions](/ocr/cpp/licensing/).
{{% /alert %}} 

## What's next

Congratulations! You have performed OCR on an image and extracted the machine-readable text from it. Read the [Developer reference](/ocr/cpp/developer-reference/) and [API reference](https://reference.aspose.com/ocr/cpp/) for details on developing advanced applications with Aspose.OCR for C++.
