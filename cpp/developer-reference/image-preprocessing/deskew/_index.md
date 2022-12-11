---
weight: 10
date: "2022-12-06"
author: "Vladimir Lapin"
type: docs
url: /cpp/deskew/
aliases:
- /cpp/working-with-the-skew-angle-of-the-image/
title: Skew correction
description: How to straighten a rotated image to improve recognition accuracy.
keywords:
- deskew
- straighten
- rotate
- tilt
- skew
- align
---

<style>
	button {
		cursor: pointer;
		margin-right: 20px;
		padding: 7px 15px;
		border: none;
		border-radius: 5px;
		background-color: #1a89d0;
		font-weight: 700;
		font-size: 15px;
		color: #ffffff;
	}

	button:hover {
		background-color: #3071a9;
	}

	button:focus {
		outline: none;
	}

	.code-sample {
		display: flex;
	}

	.code-sample > div {
		display: flex;
		align-items: center;
		padding: 5px 10px;
		border-radius: 5px;
		white-space: nowrap;
		background-color: rgba(0,0,0,5%);
		font-size: 16px;
		font-weight: 700;
	}

	.unseen {
		display: none !important;
	}

	.duo {
		position: relative;
		width: 800px;
		height: 474px;
	}

	.duo > img {
		position: absolute;
	}
</style>

When a page is fed to a flatbed scanner (mechanically or manually) or photographed with a smartphone, it is nearly impossible to achieve perfect alignment. As a result, a slight skew (tilt) inevitably occurs in scanned images or photographs.

Skew angle detection and image straightening is critical to the OCR process as it directly affects the reliability and efficiency of segmentation and text extraction. Aspose.OCR offers automated processing algorithms to correct image tilt (deskew) before proceeding to recognition.

## Detecting skew angle

To find out the skew angle, use [`get_skew()`](https://reference.aspose.com/ocr/cpp/groupAspose#gac4f58f27fb59cd89c3edb72d56cb4a18), [`get_skew_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#gab7313e1b045dd3db696de4033b7f340b), or [`get_skew_from_uri()`](https://reference.aspose.com/ocr/cpp/groupAspose#gad5c47a02a13a75d7c06ebb81ce3dd5e8) methods.

{{< tabs tabID="1" tabTotal="3" tabName1="From file" tabName2="From bytes" tabName3="From URL" >}}
{{< tab tabNum="1" >}}
```cpp
std::string image_path = "source.png";
std::double_t result = aspose::ocr::get_skew(image_path.c_str());
std::wcout << "Skew angle: " << result << L'\n';
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
std::double_t result = aspose::ocr::get_skew_from_raw_bytes(descriptor);
std::wcout << "Skew angle: " << result << L'\n';
```
{{< /tab >}}
{{< tab tabNum="3" >}}
```cpp
std::string url = "https://www.aspose.com/sample-ocr-page.png";
std::double_t result = aspose::ocr::get_skew_from_uri(url.c_str());
std::wcout << "Skew angle: " << result << L'\n';
```
{{< /tab >}}
{{< /tabs >}}

{{% alert color="primary" %}} 
Calculating a skew angle from URI is not supported in the Linux version of Aspose.OCR for C++.
{{% /alert %}}

![Skewed image](skew-origin.png)

<div id="skew-angle" class="code-sample">
	<button onclick="calculateSkewAngle(this)">Calculate skew angle</button>
	<div class="unseen"><code>&gt; Skew angle: 5.9°</code></div>
</div>
<script>
	function calculateSkewAngle(obj)
	{
		$(obj).siblings("div").removeClass("unseen");
	}
</script>

## Automatic skew correction

To automatically straighten skewed image before recognition, run the image through `OCR_IMG_PREPROCESS_AUTOSKEW` preprocessing filter or enable `correct_skew` property in [recognition settings](https://reference.aspose.com/ocr/cpp/struct/recognition_settings).

{{< tabs tabID="2" tabTotal="2" tabName1="Preprocessing filter" tabName2="Recognition settings" >}}
{{< tab tabNum="1" >}}
```cpp
std::string image_path = "source.png";
custom_preprocessing_filters filters_;
filters_.filter_1 = OCR_IMG_PREPROCESS_AUTOSKEW;
asposeocr_preprocess_page_and_save(image_path.c_str(), "result.png", filters_);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```cpp
std::string image_path = "source.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.correct_skew = true;
size_t res_len = aspose::ocr::page_settings(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
{{< /tab >}}
{{< /tabs >}}

<div class="duo">
	<img src="skew-origin.png" alt="Skewed image" />
	<img src="deskew.png" alt="Deskewed image" style="display: none;" />
</div>
<button onclick="triggerSkew(this)">Deskew image</button>
<script>
	function triggerSkew(obj)
	{
		let images = $(".duo > img");
		let skewed = images.eq(0).is(":visible");
		if(skewed)
		{
			images.eq(1).show(200);
			images.eq(0).hide(200);
			$(obj).text("Revert to original image");
		}
		else
		{
			images.eq(0).show(200);
			images.eq(1).hide(200);
			$(obj).text("Deskew image");
		}
	}
</script>

## Manual skew correction

In rare cases, automatic skew correction may incorrectly determine the angle of the image. This can happen to poor quality photos with significant perspective distortions.

To deal with such situations, you can rotate the image by the specified degree using `OCR_IMG_PREPROCESS_ROTATE` preprocessing filter or manually define the skew angle for such images using the `skew` property in [recognition settings](https://reference.aspose.com/ocr/cpp/struct/recognition_settings). The rotation angle is passed in degrees:

- `-360` to `0`: rotate counterclockwise;
- `0` to `360`: rotate clockwise.

{{< tabs tabID="3" tabTotal="2" tabName1="Preprocessing filter" tabName2="Recognition settings" >}}
{{< tab tabNum="1" >}}
```cpp
std::string image_path = "source.png";
custom_preprocessing_filters filters_;
filters_.filter_1 = OCR_IMG_PREPROCESS_ROTATE(-90);
asposeocr_preprocess_page_and_save(image_path.c_str(), "result.png", filters_);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```cpp
std::string image_path = "source.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.skew = -90;
size_t res_len = aspose::ocr::page_settings(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
{{< /tab >}}
{{< /tabs >}}

## Usage scenarios

- Automatic skew correction is recommended in almost all cases, except for perfectly straight scans.
- Manual rotation is recommended for:
    - photos of low quality;
    - images with a significant angle of inclination.
