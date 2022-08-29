---
title: Get Rectangles
type: docs
weight: 70
url: /net/get-rectangles/
---

## **Get Rectangles Paragraphs**

The following code snippet demonstrates the use of the [**GetRectangles**](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/getrectangles) method to get the bounding boxes coordinates of recognized paragraphs.

## Sample Code


```csharp
public static void GetRectangles()
{
    // Path to the image to recognize
    string imagePath = "MyImage.jpg";

    // Create OCR API
    AsposeOcr api = new AsposeOcr();
    
    // Calculate rectangles   
	// if you want to get a paragraphs  - don't set detect_areas = false	 
	List<Rectangle> rectangles = api.GetRectangles(fullPath, AreasType.PARAGRAPHS, true);

	// Print result           
	Console.WriteLine("Areas coordinates:");
	rectangles.ForEach(a => Console.WriteLine($"x:{a.X} y:{a.Y} width:{a.Width} height:{a.Height}"));
}
```

## **Get Rectangles Lines**

The following code snippet demonstrates the use of the [**GetRectangles**](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/getrectangles) method to get the bounding boxes coordinates of splitted lines.

## Sample Code


```csharp
public static void GetRectangles()
{
    // Path to the image to recognize
    string imagePath = "MyImage.jpg";

    // Create OCR API
    AsposeOcr api = new AsposeOcr();
    
    // Calculate rectangles   
	// if you set detect_areas = false you will get lines defined across the entire width of the image (useful for images with text only).
	// if you set detect_areas = true you will get lines defined in the paragrathes (useful for images with columns, pictures, and difficult structure).
	List<Rectangle> lines = api.GetRectangles(fullPath, AreasType.LINES, false);

	// Print result           
	Console.WriteLine("Areas coordinates:");
	lines.ForEach(a => Console.WriteLine($"x:{a.X} y:{a.Y} width:{a.Width} height:{a.Height}"));
}
```

## **Get Rectangles Words**

The following code snippet demonstrates the use of the [**GetRectangles**](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/getrectangles) method to get the bounding boxes coordinates of words.

## Sample Code


```csharp
public static void GetRectangles()
{
    // Path to the image to recognize
    string imagePath = "MyImage.jpg";

    // Create OCR API
    AsposeOcr api = new AsposeOcr();
    
    // Calculate rectangles   
	List<Rectangle> lines = api.GetRectangles(fullPath, AreasType.WORDS, false);

	// Print result           
	Console.WriteLine("Areas coordinates:");
	lines.ForEach(a => Console.WriteLine($"x:{a.X} y:{a.Y} width:{a.Width} height:{a.Height}"));
}
```