---
title: Customer Image Correction Using Preprocessing Filters
type: docs
weight: 75
url: /net/customer-image-correction-with-preprocessing-filters/
---
## **Customer Image Correction Preprocessing Filters**
Aspose.OCR for .NET provides to option to specify custom preprocessing operations for image quality correction. 
For this, the API provides the [**RecognitionSettings.PreprocessingFilters**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/preprocessingfilters) property. 
You can pass the instance of the [**RecognitionSettings**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings) class to the [**RecognizeImage**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizeimage/index) method of the [**AsposeOcr**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr) class.

The following code snippet demonstrates the use of the [**PreprocessingFilters**](https://apireference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter) provides custom image quality correction. 
Usually, preprocessing operations done automatically, but in some cases, using [**PreprocessingFilters**](https://apireference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter) you can get a better recognition result.
You can customize preprocessing operations directly in method [**RecognizeImage**](https://apireference.aspose.com/ocr/net/aspose.ocr.asposeocr/recognizeimage/methods/5) or before recognitionprocess using [**PreprocessImage**](https://apireference.aspose.com/ocr/net/aspose.ocr.asposeocr/preprocessimage/methods/1) method.


## Sample Code

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the documents directory.
	string dataDir = RunExamples.GetDataDir_OCR();

	// Initialize an instance of AsposeOcr
	AsposeOcr api = new AsposeOcr();

	// set filters as you need
            PreprocessingFilter filters = new PreprocessingFilter
            {
                 PreprocessingFilter.Binarize(),
                 PreprocessingFilter.Threshold(220),
                 PreprocessingFilter.ToGrayScale(),
                 PreprocessingFilter.Invert(),
                 PreprocessingFilter.Rotate(20),
                 PreprocessingFilter.Resize(3000,3000, Aspose.OCR.Filters.InterpolationFilterType.Box),
                 PreprocessingFilter.Scale(0.5f),
                 PreprocessingFilter.Dilate(),
            };

    // case 1
            // preprocess input image and get the MemoryStream with output image after preprocessing. Then use RecognizeImage.
            MemoryStream ms = api.PreprocessImage(image, filters);

            // save image into file system as you need
            using (FileStream file = new FileStream("result.png", FileMode.Create, System.IO.FileAccess.Write))
            {
                ms.WriteTo(file);
            }

            // recognize process
            var res = api.RecognizeImage(ms, new RecognitionSettings());
			// Display the recognized text
            Console.WriteLine(res.RecognitionText);

    // case 2 
            // use filters as settings in recognition process
            var res2 = api.RecognizeImage(image, new RecognitionSettings { PreprocessingFilters = filters });
			// Display the recognized text
            Console.WriteLine(res2.RecognitionText);
			
			
{{< /highlight >}}


