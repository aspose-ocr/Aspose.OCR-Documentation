---
title: Automatic noise removal
type: docs
weight: 90
url: /java/denoising-ai/
---

Dirt, spots, scratches, glare, unwanted gradients, and other image defects can interfere with recognition and significantly reduce OCR accuracy. Aspose.OCR for Java provides a powerful Binarized Neural Network (BNN) that can clean up an image and reduce or completely remove noise.

While Aspose.OCR for Java automatically pre-processes images before recognition, automatic noise removal is resource and time intensive and can reduce recognition speed on entry-level computers. Therefore, it is **disabled** by default.

To enable automatic noise removal, call [`setAutoDenoising(true)`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setAutoDenoising-boolean-) method of [`RecognitionSettings`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings) class instance and pass this instance to the [`RecognizePage`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#RecognizePage) method.

## Example

The following code snippet demonstrates how to specify the region recognition method. Visit https://github.com/aspose-ocr/Aspose.OCR-for-Java for the full project and sample data files.

{{< highlight java >}}
// Image path
String file= "image.png";
// Create instance of OCR API
AsposeOCR api = new AsposeOCR();
// Turn on automatic noise removal AI
RecognitionSettings settings = new RecognitionSettings();
settings.setAutoDenoising(true);
// Recognize image and output results
RecognitionResult result = api.RecognizePage(file, settings);
System.out.println(result.recognitionText);
{{< /highlight >}}
