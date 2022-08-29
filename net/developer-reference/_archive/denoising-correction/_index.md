---
title: Automatic noise removal
type: docs
weight: 77
url: /net/denoising-correction/
---

Dirt, spots, scratches, glare, unwanted gradients, and other image defects can interfere with recognition and significantly reduce OCR accuracy. Aspose.OCR for .NET provides a powerful Binarized Neural Network (BNN) that can clean up an image and reduce or completely remove noise.

While Aspose.OCR for NET automatically pre-processes images before recognition, automatic noise removal is resource and time intensive and can reduce recognition speed on entry-level computers. Therefore, it is **disabled** by default.

To enable automatic denoising, pass an instance of [RecognitionSettings](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/) class with [`AutoDenoising`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/autodenoising/) property set to `true` and pass this instance to the [`RecognizeImage`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizeimage/#recognizeimage) method.

## Example

The following code snippet demonstrates how to enable automatic noise removal. Visit https://github.com/aspose-ocr/Aspose.OCR-for-.NET for the full project and sample data files.

{{< highlight csharp >}}
// Path to the sample files directory
string dataDir = RunExamples.GetDataDir_OCR();
// Image path
String imagePath = dataDir + "0001460985.Jpeg";
// Create instance of OCR API
AsposeOcr api = new AsposeOcr();
// Remove noise and recognize the image 
var recognitionResults = api.RecognizeImage(imagePath, new RecognitionSettings {AutoDenoising = true});
{{< /highlight >}}
