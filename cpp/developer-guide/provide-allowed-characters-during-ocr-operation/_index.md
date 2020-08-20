---
title: Provide allowed characters during OCR operation
type: docs
weight: 50
url: /cpp/provide-allowed-characters-during-ocr-operation/
---


In case you know the characters that are present in the image and want to specify those characters during the OCR process, you can use the two methods provided by the Aspose.OCR for C++ API.

- [page_abc](https://apireference.aspose.com/ocr/cpp/a00008#ga365b20dd01255d55fec539c9ae1660fd): This method works similarly to the [page](https://apireference.aspose.com/ocr/cpp/a00008#ga933c34225334b415cfa215e6f6336887) method except that it accepts the allowed characters as a parameter.
- [line_abc](https://apireference.aspose.com/ocr/cpp/a00008#ga67f910e01a306a072d3243ed6ec308da): This method works similarly to the [line](https://apireference.aspose.com/ocr/cpp/a00008#gae9481818444957d7bfa6da941ef88aea) method except that it accepts the allowed characters as a parameter.

Using these methods will ensure that only the provided characters are matched during the OCR process. The following code snippets demonstrate the use of [page_abc](https://apireference.aspose.com/ocr/cpp/a00008#ga365b20dd01255d55fec539c9ae1660fd) and [line_abc](https://apireference.aspose.com/ocr/cpp/a00008#ga67f910e01a306a072d3243ed6ec308da) methods
## **Provide allowed characters for page**
{{< gist "aspose-com-gists" "0a96b16b37da1f556e7081063782ec02" "Aspose.OCR-for-C-main-SpecifyAllowedCharacters.cpp" >}}
## **Provide allowed characters for line**
{{< gist "aspose-com-gists" "0a96b16b37da1f556e7081063782ec02" "Aspose.OCR-for-C-main-RecognizeLineWithAllowedCharacters.cpp" >}}
