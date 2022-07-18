---
title: Get Rectangles
type: docs
weight: 30
url: /cpp/get-rectangles/
---

## **Get Rectangles Paragraphs**

The following code snippet demonstrates the use of the [**get_rectangles()**](https://reference.aspose.com/ocr/cpp) method to get the bounding boxes coordinates of recognized paragraphs.

## Sample Code

[Supported Characters](/ocr/cpp/get-rectangles/)

```cpp
void GetRectanglesParagraphs() {
	std::string image_path = "../Data/Source/sample.png";

	// if you want to get a paragraphs  - don't set all_image = true
	// first calculate rectangles number
	size_t res_len = aspose::ocr::get_rectangles_number(image_path.c_str(), areas_type::paragraphs, false);
	std::wcout << "paragraphs number: " << res_len << std::endl;

	// allocate memory for rectangles
	rect* rectangles = new rect[res_len];
	// be careful and set the same settings for get_rectangles_number and get_rectangles
	res_len = aspose::ocr::get_rectangles(image_path.c_str(), areas_type::paragraphs, false, rectangles, res_len);

	std::wcout << "paragraphs: " << std::endl;
	for (size_t i = 0; i < res_len; i++)
	{
		std::wcout << " x: " << rectangles[i].x << " y: " << rectangles[i].y << " width: " << rectangles[i].width << " height: " << rectangles[i].height << std::endl;
	}
	delete[] rectangles;
}
```

## **Get Rectangles Lines**

The following code snippet demonstrates the use of the [**get_rectangles()**](https://reference.aspose.com/ocr/cpp) method to get the bounding boxes coordinates of recognized lines.

## Sample Code

[Supported Characters](/ocr/cpp/get-rectangles/)

```cpp
void GetRectanglesLines() {
	std::string image_path = "../Data/Source/sample.png";

	// if you want to get lines in paragraphs  - set all_image = false (useful for images with columns, pictures, and difficult structure
	// in case you set all_image = true - you will get lines defined across the entire width of the image (useful for images with text only)

	// first calculate rectangles number
	size_t res_len = aspose::ocr::get_rectangles_number(image_path.c_str(), areas_type::lines, false);
	std::wcout << "lines number: " << res_len << std::endl;

	// allocate memory for rectangles
	rect* rectangles = new rect[res_len];
	// be careful and set the same settings for get_rectangles_number and get_rectangles
	res_len = aspose::ocr::get_rectangles(image_path.c_str(), areas_type::lines, false, rectangles, res_len); 

	std::wcout << "lines: " << std::endl;
	for (size_t i = 0; i < res_len; i++)
	{
		std::wcout << " x: " << rectangles[i].x << " y: " << rectangles[i].y << " width: " << rectangles[i].width << " height: " << rectangles[i].height << std::endl;
	}
	delete [] rectangles;
}
```

## **Get Words Rectangles**

The following code snippet demonstrates the use of the [**get_rectangles()**](https://reference.aspose.com/ocr/cpp) method to get the bounding boxes coordinates of recognized words. Available from v22.4.

## Sample Code

[Supported Characters](/ocr/cpp/get-rectangles/)

```cpp
void GetRectanglesLines() {
	std::string image_path = "../Data/Source/sample.png";	

	// first calculate words number
	size_t res_len = aspose::ocr::get_rectangles_number(image_path.c_str(), areas_type::words, false);
	std::wcout << "words number: " << res_len << std::endl;

	// allocate memory for rectangles
	rect* rectangles = new rect[res_len];
	// be careful and set the same settings for get_rectangles_number and get_rectangles
	res_len = aspose::ocr::get_rectangles(image_path.c_str(), areas_type::words, false, rectangles, res_len); 

	std::wcout << "words: " << std::endl;
	for (size_t i = 0; i < res_len; i++)
	{
		std::wcout << " x: " << rectangles[i].x << " y: " << rectangles[i].y << " width: " << rectangles[i].width << " height: " << rectangles[i].height << std::endl;
	}
	delete [] rectangles;
}
```

## **Get Words Rectangles From URI**

The following code snippet demonstrates the use of the [**get_rectangles_from_uri()**](https://reference.aspose.com/ocr/cpp/groupAspose#ga270c57b8595cd911c7cf2e68fcc624af) method to get the bounding boxes coordinates of recognized words. Available from v22.4.

## Sample Code

[Supported Characters](/ocr/cpp/get-rectangles-from-uri/)

```cpp
void GetRectanglesLines() {
	const char* uri = "https://assets.htmlacademy.ru/content/blog/94/text-bottom-1@1x.png";

	// first calculate words number
	size_t res_len = aspose::ocr::get_rectangles_number_from_uri(uri, areas_type::words, false);
	std::wcout << "words number: " << res_len << std::endl;

	// allocate memory for rectangles
	rect* rectangles = new rect[res_len];
	// be careful and set the same settings for get_rectangles_number and get_rectangles
	res_len = aspose::ocr::get_rectangles_from_uri(uri, areas_type::words, false, rectangles, res_len); 

	std::wcout << "words: " << std::endl;
	for (size_t i = 0; i < res_len; i++)
	{
		std::wcout << " x: " << rectangles[i].x << " y: " << rectangles[i].y << " width: " << rectangles[i].width << " height: " << rectangles[i].height << std::endl;
	}
	delete [] rectangles;
}
```
