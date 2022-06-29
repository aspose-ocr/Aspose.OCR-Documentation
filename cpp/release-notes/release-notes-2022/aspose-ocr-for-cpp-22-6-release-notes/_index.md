---
title: Aspose.OCR for CPP 22.6 Release Notes
type: docs
weight: 83
url: /cpp/aspose-ocr-for-cpp-22.6-release-notes/
---

{{% alert color="primary" %}}

This page contains release notes for Aspose.OCR for C++ 22.6.

{{% /alert %}}

{{% alert color="primary" %}}

**GPU version: 21.7.0**

{{% /alert %}}

## All Features

|Key|Summary|Category|
|---|---|---|
|OCRCPP-278| Integrate code for the XML and JSON serialization |Enhancement|
|OCRCPP-277| Integrate pre and post processing algorithms for Binarization neural network |Enhancement|
|OCRCPP-275| Integrate Binarization neural network + tests |Enhancement|
|OCRCPP-274| Table recognition |Enhancement|

## Enhancements

- added new ML model for image denoising
- added support for output format JSON and expaneded fields in JSON serialized result
- added new detection areas mode - TABLE


## Public API and Backwards Incompatible Changes

### New API

|Enum|Fields|
|---|---|
|file_format |	<div><p>format_json</p></div>	|
|detect_areas_mode_enum |	<div><p>TABLE</p></div>	|
	
|Settings|Description|
|---|---|
|bool auto_denoising|
	<div><p>Enables the use of an additional neural network for the image before recognition. Useful for images with noice, spots, flares, gradients, foreign elements.</p></div>
	|


### Removed APIs

No Changes

## Example (C++17 since filesystem)

{{< highlight cpp >}}

#include <iostream>
#include <aspose_ocr.h>
#include <filesystem>
#include <corecrt_io.h>
#include <fcntl.h>
int main()
{
_setmode(_fileno(stdout), _O_U16TEXT);
//Current directory const
std::filesystem::path path{ std::filesystem::current_path() };
/* asposeocr_set_license */
const std::string lic = "/Aspose.Total.lic";
std::filesystem::path license = path.string() + lic;
asposeocr_set_license(license.string().c_str());
/* asposeocr_set_license */
bool lic_result = asposeocr_get_state();


// Recognize and save json
	
    RecognitionSettings settings;
    set.save_format = file_format::format_json;
    asposeocr_page_save("img1.jpg;img2.jpg", "result.json", set);
	
// Recognize and get json
// Prepare buffer for result (in symbols, len_byte = len * sizeof(wchar_t))
	const size_t len = 4096;
    wchar_t buffer[len] = { 0 };	
    RecognitionSettings settings;
    set.format = export_format::json;
    size_t result = asposeocr_page_settings(image.c_str(), buffer, len, settings);
    std::wcout << buffer;	
	
// Recognize with denoising

	const string image = "img.jpg";

	// Prepare buffer for result (in symbols, len_byte = len * sizeof(wchar_t))
	const size_t len = 4096;
    wchar_t buffer[len] = { 0 };
    RecognitionSettings settings;
    set.auto_denoising = true;
    size_t result = asposeocr_page_settings(image.c_str(), buffer, len, settings);
    std::wcout << buffer;	
}

{{< /highlight >}}
