---
weight: 20
date: "2022-12-06"
author: "Vladimir Lapin"
type: docs
url: /cpp/denoise/
feedback: OCRCPP
title: Noise removal
description: How to remove dirt, spots, scratches, glare, and other image defects to improve recognition accuracy.
aliases:
- /cpp/custom-image-correction-with-auto-contrast-denoising/
keywords:
- denoise
- defect
- noise
- clean
- clear
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

	.duo {
		position: relative;
		width: 569px;
		height: 376px;
		margin-bottom: 20px;
	}

	.duo > img {
		position: absolute;
	}
</style>

Dirt, spots, scratches, glare, unwanted gradients, and other noise are a common problem when scanning low-quality sources such as newspapers or old books, or when taking photographs. These image defects can interfere with recognition, significantly reduce the accuracy of OCR, and may cause spots to be misrecognised as characters.

Aspose.OCR provides automated processing algorithms that remove noise from images before proceeding to recognition.

{{% alert color="primary" %}} 
Noise removal automatically converts the image to [black and white](/ocr/cpp/binarization/#automatically-converting-the-image-to-black-and-white).
{{% /alert %}}

## Automatic noise removal

To automatically remove the noise from the image before recognition, run the image through `OCR_IMG_PREPROCESS_AUTODENOISING` preprocessing filter or enable `auto_denoising` property in [recognition settings](https://reference.aspose.com/ocr/cpp/struct/recognition_settings).

{{< tabs tabID="1" tabTotal="2" tabName1="Preprocessing filter" tabName2="Recognition settings" >}}
{{< tab tabNum="1" >}}
```cpp
std::string image_path = "source.png";
custom_preprocessing_filters filters_;
filters_.filter_1 = OCR_IMG_PREPROCESS_AUTODENOISING;
asposeocr_preprocess_page_and_save(image_path.c_str(), "result.png", filters_);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```cpp
std::string image_path = "source.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.auto_denoising = true;
size_t res_len = aspose::ocr::page_settings(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
{{< /tab >}}
{{< /tabs >}}

<div class="duo">
	<img src="origin.png" alt="Noisy image" />
	<img src="result.png" alt="Denoised image" style="display: none;" />
</div>
<button onclick="triggerSkew(this)">Remove noise</button>
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
			$(obj).text("Remove noise");
		}
	}
</script>

## Usage scenarios

Automatic noise removal is recommended for the following images:

- Photos, especially those taken in low light conditions.
- Old books.
- Newspapers.
- Postcards.
- Text with a photo or picture as a background.
- Scanned papers with spots and dirt.

However, noise removal can reduce recognition accuracy when working with poor-quality prints, as it can lead to the loss of important details, such as light punctuation or heavily fragmented characters.
