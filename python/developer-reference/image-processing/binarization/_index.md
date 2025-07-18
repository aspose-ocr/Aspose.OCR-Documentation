---
weight: 50
date: "2023-08-27"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/binarization/
feedback: OCRPYNET
title: Binarization
description: How to convert an image to black and white using Aspose.OCR for Python via .NET either automatically or by manually specifying a threshold.
keywords:
- black
- white
- pixel
- binary
- monochrome
---

<style>
	button {
		cursor: pointer;
		padding: 7px 15px;
		border-top: solid 2px #1a89d0;
		border-bottom: solid 2px #1a89d0;
		border-left: solid 1px #1a89d0;
		border-right: solid 1px #1a89d0;
		background-color: #ffffff;
		font-weight: 700;
		font-size: 15px;
		color: #1a89d0;
	}

	button:focus {
		outline: none;
	}

	.sequence {
		position: relative;
		width: 600px;
		height: 300px;
		margin-top: 30px;
		margin-bottom: 30px;
		box-shadow: 5px 7px 10px 0px rgba(0,0,0,0.3);
	}

	.sequence > img {
		position: absolute;
	}

	.sequence > img:not(:first-child) {
		display: none;
	}

	.toolbar {
		display: flex;
		align-items: center;
		margin-bottom: 25px;
	}

	.toolbar > span {
		margin-right: 15px;
		font-weight: 700;
	}

	.toolbar > button {
		width: 90px;
	}

	.toolbar > button.active {
		background-color: #1a89d0;
		color: #ffffff;
	}

	.toolbar > button:not(.active):hover {
		background-color: #1a89d0;
		color: #ffffff;
	}

	.toolbar > button:nth-child(2) {
		border-left-width: 2px;
		border-top-left-radius: 5px;
		border-bottom-left-radius: 5px;
	}

	.toolbar > button:last-child {
		border-right-width: 2px;
		border-top-right-radius: 5px;
		border-bottom-right-radius: 5px;
	}

	.results > *:not(:first-child) {
		display: none;
	}

</style>

While you can extract text from color or grayscale scans or photographs, Aspose.OCR for Python via .NET engine always uses black and white images to detect text and perform automatic corrections. The conversion to black-and-white is performed automatically; this process is called _binarization_.

## Automatically converting the image to black and white

By default, Aspose.OCR for Python via .NET automatically calculates the optimal binarization parameters. To convert the image to black and white before performing the recognition, apply `binarize` processing filter:

{{% alert color="primary" %}}
The image is automatically converted to black and white when applying the following filters:

- [Noise removal](/ocr/python-net/denoise/)
- [Contrast correction](/ocr/python-net/contrast/)
- [Dilation](/ocr/python-net/dilate/)
{{% /alert %}}

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Initialize image processing
filters = PreprocessingFilter()
filters.add(PreprocessingFilter.binarize())
# Add image to the recognition batch and apply processing filter
input = OcrInput(InputType.SINGLE_IMAGE, filters)
input.add("source.png")
# Save processed image to the "result" folder
ImageProcessing.save(input, "result")
# Recognize the image
result = api.recognize(input)
# Print recognition result
print(result[0].recognition_text)
```

## Using binarization threshold

In some rare cases, you may need to override the automatic binarization settings to get more accurate recognition results:

- Poor quality printouts such as faxes or receipts on thermal paper.
- Photos with glares and gradients taken in low-light conditions.
- Multicolored texts.

If you notice that part of the text disappears from the recognition results, try manually specifying the **threshold** criteria that determine whether a pixel is considered black or white. If a pixel is lighter than the threshold, it is considered a white pixel, otherwise it is considered a black pixel. In other words, the higher the threshold value, the more content will be sent for recognition, including words printed in very light colors. If the threshold set to `0`, the black and white are assigned automatically based on the content of the image.

To specify binarization threshold, provide it in `threshold` processing filter. To rely on automatic processing, do not add a filter.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Initialize image processing
filters = PreprocessingFilter()
filters.add(PreprocessingFilter.threshold(150))
# Add image to the recognition batch and apply processing filter
input = OcrInput(InputType.SINGLE_IMAGE, filters)
input.add("source.png")
# Save processed image to the "result" folder
ImageProcessing.save(input, "result")
# Recognize the image
result = api.recognize(input)
# Print recognition result
print(result[0].recognition_text)
```

### Live demo

<div class="sequence">
	<img src="source.png" alt="Source" threshold="-1" />
	<img src="result-0.png" alt="Binarization threshold: auto" threshold="0" />
	<img src="result-50.png" alt="Binarization threshold: 50" threshold="50" />
	<img src="result-100.png" alt="Binarization threshold: 100" threshold="100" />
	<img src="result-150.png" alt="Binarization threshold: 150" threshold="150" />
	<img src="result-200.png" alt="Binarization threshold: 200" threshold="200" />
</div>

<div class="toolbar">
	<span>Threshold:</span>
	<button threshold="-1" class="active" onclick="showResult(this)"><i>Source</i></button>
	<button threshold="0" onclick="showResult(this)">Auto</button>
	<button threshold="50" onclick="showResult(this)">50</button>
	<button threshold="100" onclick="showResult(this)">100</button>
	<button threshold="150" onclick="showResult(this)">150</button>
	<button threshold="200" onclick="showResult(this)">200</button>
</div>

<script>
	function showResult(obj)
	{
		let button = $(obj);
		let threshold=button.attr("threshold");
		$(".sequence > img").hide();
		$(`.sequence > img[threshold="${threshold}"]`).show();
		$(".results > *").hide();
		$(`.results > *[threshold="${threshold}"]`).show();
		$(".toolbar > button").removeClass("active");
		button.addClass("active");
		$("#thresholdvalue").text((threshold<0)?0:threshold);
	}


"Optical character recognition or is the electronic or conversion of images of typed, handwritten ore text into machine-encoded text, whether from a scanned document, a photo of a document, a scene-photo or from subtitle text superImposed on an image."

</script>

#### Code snippet

<div class="highlight"><pre tabindex="0" class="chroma"><code class="language-python" data-lang="python"><span class="line"><span class="cl"><span class="c1"># Instantiate Aspose.OCR API</span>
</span></span><span class="line"><span class="cl"><span class="n">api</span> <span class="o">=</span> <span class="n">AsposeOcr</span><span class="p">()</span>
</span></span><span class="line"><span class="cl"><span class="c1"># Initialize image processing</span>
</span></span><span class="line"><span class="cl"><span class="n">filters</span> <span class="o">=</span> <span class="n">PreprocessingFilter</span><span class="p">()</span>
</span></span><span class="line"><span class="cl"><span class="n">filters</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">PreprocessingFilter</span><span class="o">.</span><span class="n">threshold</span><span class="p">(</span><span class="mi" id="thresholdvalue">0</span><span class="p">))</span>
</span></span><span class="line"><span class="cl"><span class="c1"># Add image to the recognition batch and apply processing filter</span>
</span></span><span class="line"><span class="cl"><span class="nb">input</span> <span class="o">=</span> <span class="n">OcrInput</span><span class="p">(</span><span class="n">InputType</span><span class="o">.</span><span class="n">SINGLE_IMAGE</span><span class="p">,</span> <span class="n">filters</span><span class="p">)</span>
</span></span><span class="line"><span class="cl"><span class="nb">input</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="s2">"source.png"</span><span class="p">)</span>
</span></span><span class="line"><span class="cl"><span class="c1"># Recognize the image</span>
</span></span><span class="line"><span class="cl"><span class="n">result</span> <span class="o">=</span> <span class="n">api</span><span class="o">.</span><span class="n">recognize</span><span class="p">(</span><span class="nb">input</span><span class="p">)</span>
</span></span><span class="line"><span class="cl"><span class="c1"># Print recognition result</span>
</span></span><span class="line"><span class="cl"><span class="nb">print</span><span class="p">(</span><span class="n">result</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span><span class="o">.</span><span class="n">recognition_text</span><span class="p">)</span>
</span></span></code></pre></div>

#### Recognition result

<div class="results">

<div class="highlight" threshold="-1"><pre tabindex="0" style="background-color:#f8f8f8;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code id="results"><span style="color:#8f5902;font-style:italic;">&lt;specify threshold value to recognize the image&gt;</span></code></pre></div>

<div class="highlight" threshold="0"><pre tabindex="0" style="background-color:#f8f8f8;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code id="results">Optical character recognition or
is the electronic or
conversion of images of typed,
handwritten ore text into
machine-encoded text, whether from a
scanned document, a photo of a document,
a scene-photo or from subtitle text
superImposed on an image.
</code></pre></div>

<div class="highlight" threshold="50"><pre tabindex="0" style="background-color:#f8f8f8;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code id="results">Optical character recognition or
Is the or
conversion of images of typed,
or printed text into
machine-encoded text, whether from a
scanned document,
a or from subtitle text
superimposed on an image.
</code></pre></div>

<div class="highlight" threshold="100"><pre tabindex="0" style="background-color:#f8f8f8;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code id="results">Optical character recognition or
is the electronic or
conversion of images of typed,
or printed text into
machine-encoded text, whether from a
scanned document, a photo of a document,
a or from subtitle text
superimposed or an Image.
</code></pre></div>

<div class="highlight" threshold="150"><pre tabindex="0" style="background-color:#f8f8f8;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code id="results">Optical character recognition or
is the electronic or
conversion of images of typed,
handwritten or printed text into
machine-encoded text, whether from a
scanned document,a photo of a document,
a scene-photo or from subtitle text
superimposed on an image.
</code></pre></div>

<div class="highlight" threshold="200"><pre tabindex="0" style="background-color:#f8f8f8;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code id="results">Optical character recognition or optical
character reader is the electronic or
mechanical conversion of images of typed,
handwritten or printed text into
machine-encoded text, whether from a
scanned document,a photo of a document,
a scene-photo or from subtitle text
superimposed on an image.
</code></pre></div>

</div>

## Usage scenarios

Binarization is always used for text detection and automatic image corrections. Also, monochrome images take up significantly less disk space than full color images, so you can use binarization for archiving digitized documents.
