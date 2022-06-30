---
title: Aspose.OCR for Java 22.6 - Release Notes
type: docs
weight: 14
url: /java/aspose-ocr-for-java-22-6-release-notes/
---

{{% alert color="primary" %}}

This page contains release notes information for Aspose.OCR for Java 22.6

{{% /alert %}}

{{% alert color="primary" %}}

**GPU version: 21.6.0**

{{% /alert %}}

## All Features

|Key|Summary|Category|
|---|---|---|
|OCRJAVA-254| Integrate pre and post processing algorithms for Binarization neural network |Enhancement|
|OCRJAVA-250| Integrate Binarization neural network + tests |Enhancement|
|OCRJAVA-247| Fix the bug with PDF creation |Bugfix|
|OCRJAVA-249| Added a new detection mode for better identification and recognition of tabular structures. |Enhancement|

## Enhancements

The next opportunities:

- added Binarization neural network and autoDenoising settings
- fixed PDF creation
- add Table recognition

## Public API and Backwards Incompatible Changes

### New API

- added field TABLE to the DetectAreasMode enum
- added method setAutoDenoising(bool) to the RecognitionSettings class


### Removed APIs

- none


### Will be deprecated

- none

## Usage Example

{{< highlight java >}}

import static java.lang.System.out;

import java.awt.Rectangle;
import java.io.IOException;

import com.aspose.ocr.AsposeOCR;
import com.aspose.ocr.DocumentRecognitionSettings;
import com.aspose.ocr.CharactersAllowedType;
import com.aspose.ocr.License;
import com.aspose.ocr.RecognitionResult;
import com.aspose.ocr.RecognitionResult.LinesResult;
import com.aspose.ocr.metered.Metered;


public class App {
       public static void main(String[] args) {

         // set license   
        License.setLicense("Aspose.Total.lic");
        boolean resLicense = License.isValid();
        out.println("License is :" + resLicense);

  		String file= "image.png";		

        // Create api instance
        AsposeOCR api = new AsposeOCR();
	    RecognitionSettings settings = new RecognitionSettings();
		
		// for images with scan artifacts, distortion, spots, flares, gradients, foreign elements set denoising filter
		settings.setAutoDenoising(true);
		
		// for tables images set mode TABLE 
		settings.setDetectAreasMode(DetectAreasMode.TABLE);
        RecognitionResult result = api.RecognizePage(file, settings);
        System.out.println("result preprocessed image:\n"+result.recognitionText);
    }	
}

{{< /highlight >}}
