---
title: Get words coordinates
type: docs
weight: 30
url: /java/get-words-coordinates/
---

## **Get words coordinates**
Aspose.OCR for Java provides the method to get the result as coordinates of the paragraphs, lines, words [**getTextAreas**](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#getTextAreas ). 
For this, the API provides the enum[**AreasType**](https://reference.aspose.com/ocr/java/com.aspose.ocr/AreasType ).

## Sample Code

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-Java
	// The path to the documents directory.
	String dataDir = Utils.getSharedDataDir(PerformOCROnPage.class);

	// The image path
	String imagePath = dataDir + "p3.png";

	// Initialize an instance of AsposeOcr
	 AsposeOCR api = new AsposeOCR();

        // Set license 
        License.setLicense("Aspose.Total.lic");
        
        // Get image file for recognize     
        String imgPath = p.txt";

		// Create api instance
        AsposeOCR api = new AsposeOCR();
		
	    // get words coordinates
        ArrayList<Rectangle> result = api.getTextAreas(imgPath, AreasType.WORDS, false);
		
		System.out.println("words amount: " + result.size());
		
		for(int i = 0; i < result.size(); i++){
    		 Rectangle rect = result.get(i);
    		 System.out.print("x: "+rect.x);
			 System.out.print(" y: "+rect.y);
			 System.out.print(" width: "+rect.width);
			 System.out.println(" height: "+rect.height);
    	}
    	}	
    }
    
   
{{< /highlight >}}


