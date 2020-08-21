---
title: Provide allowed characters during OCR operation
type: docs
weight: 50
url: /cpp/provide-allowed-characters-during-ocr-operation/
---


In case you know the characters that are present in the image and want to specify those characters during the OCR process, you can use the two methods provided by the Aspose.OCR for C++ API.

- **[page_abc](https://apireference.aspose.com/ocr/cpp/a00005#ga0e6cc74793adbf5efdf4028d7f9161f9)**: This method works similarly to the **[page](https://apireference.aspose.com/ocr/cpp/a00005#gae4fb9b76d4b358a98b33909cc274ff82)** method except that it accepts the allowed characters as a parameter.
- **[line_abc](https://apireference.aspose.com/ocr/cpp/a00005#gaf65e3c2c22843a71db64571b70ba1a12)**: This method works similarly to the **[line](https://apireference.aspose.com/ocr/cpp/a00005#ga00aec23aeebdb45943cfc6db33539540)** method except that it accepts the allowed characters as a parameter.

Using these methods will ensure that only the provided characters are matched during the OCR process. The following code snippets demonstrate the use of **[page_abc](https://apireference.aspose.com/ocr/cpp/a00005#ga0e6cc74793adbf5efdf4028d7f9161f9)** and **[line_abc](https://apireference.aspose.com/ocr/cpp/a00005#gaf65e3c2c22843a71db64571b70ba1a12)** methods

## **Provide allowed characters for page**

{{< gist "aspose-com-gists" "0a96b16b37da1f556e7081063782ec02" "Aspose.OCR-for-C-main-SpecifyAllowedCharacters.cpp" >}}

## **Provide allowed characters for line**

{{< gist "aspose-com-gists" "0a96b16b37da1f556e7081063782ec02" "Aspose.OCR-for-C-main-RecognizeLineWithAllowedCharacters.cpp" >}}
