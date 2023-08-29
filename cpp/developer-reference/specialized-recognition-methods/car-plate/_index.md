---
weight: 10
date: "2023-07-20"
author: "Vladimir Lapin"
type: docs
url: /cpp/vehicle-id-recognition/
feedback: OCRCPP
title: Extracting text from vehicle license plate images
description: How to automatically extract text from scanned or photographed vehicle license plates.
keywords:
- read
- extract
- OCR
- recognize
- check
- image
- photo
- vehicle
- license plate
- car plate
- number
---

Aspose.OCR offers a special recognition algorithm that extracts text from vehicle license plates, including dark and blurry photos. The resulting text can then be automatically saved to the database or automatically verified.

To extract text from a vehicle license plate image, use `asposeocr_recognize_vehicle_license_plate()` function. This function also allows you to customize recognition accuracy, performance, and other [settings](/ocr/cpp/settings/).

```cpp
// Provide the car license plate image
string file = current_dir + "/black_mercedes.png";
AsposeOCRInput source;
source.url = file.c_str();
std::vector<AsposeOCRInput> content = { source };
// Set recognition language
RecognitionSettings settings;
settings.language_alphabet = language::eng;
// Extract text from the image
auto result = asposeocr_recognize_vehicle_license_plate(content.data(), content.size(), settings);
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::wcout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```
