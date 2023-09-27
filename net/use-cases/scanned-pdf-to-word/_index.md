---
weight: 30
date: "2023-09-26"
author: "Vladimir Lapin"
type: docs
url: /net/scan-to-word/
feedback: OCRNET
title: Converting a scan to editable document
description: Create an editable document in Microsoft Word format from a scanned image, PDF or even a photo.
keywords:
- scan
- PDF
- edit
- Word
- modify
- change
---

While many businesses, organizations and individuals have been actively working on reducing their reliance on paper documents, this is still the most widespread format for storage and sharing. For example, scans of paper documents are actively used to exchange signed contracts, NDA's, invoices and other legally binding documents.

Scanned documents backed by physical archives are sufficient for regulatory compliance, legal purposes, long-term backup and redundancy. However, business cases frequently arise for creating new documents based on existing scanned content or portions of existing documents. Here are some common scenarios where this practice is advantageous:

- Quickly assemble a new contract or other legal agreement using standard clauses or terms from the existing ones.
- Update minor details, such as dates or numbers; fix typos.
- Compile relevant scanned documents into a single, coherent document.
- Incorporate blocks of scanned content into reports, presentations, training materials, and so on.

**Aspose.OCR for .NET** makes it easy to convert a scanned image, an image-based PDF, or even a photo into an editable DOCX or RTF document or Microsoft Excel spreadsheet (XLSX). Content is recognized with high accuracy and speed, saving you the time and effort of manual typing and ensuring there are no human errors, especially when working with large volumes of text. The library supports [28 languages](/ocr/net/recognition-languages/) based on Latin, Cyrillic and Asian scrips which makes it applicable for most businesses and organizations on the global scale. All popular typefaces such as Arial, Times New Roman, Courier New, Tahoma, Calibri and more in regular, bold and italic styles are detected and recognized.

In the example below, we will show you how to convert a signed contract scanned to PDF into an editable Microsoft Word document. You will only need 24 lines of code (including comments) - see for yourself.

## Sample document

Use your own scan or [download](Delivery-Agreement.pdf) the sample scanned agreement in PDF format.

## Preparation

1. Get a [trial license](/ocr/net/licensing/) to make sure that all text is recognized without limitations.
2. Create a new C# project in Visual Studio. You can use a very basic project template, such as **Console App**.
3. [Install](/ocr/net/installation/) **Aspose.OCR** (CPU-based) NuGet package to the project.
4. Save the scanned document to **bin\\Debug** or **bin\\Debug\\net6.0** directory of the project under the name `Delivery-Agreement.pdf`.

## Coding

1. Declare `Aspose.OCR` namespace to improve the code readability:
   ```csharp
   using Aspose.OCR;
   ```
2. Apply a [license](/ocr/net/licensing/#applying-a-developer-or-site-license):
   ```csharp
   License license = new License();
   license.SetLicense("Aspose.OCR.lic");
   ```
3. [Load](/ocr/net/ocrinput/) the scan. You can also use a full path to the file.
   ```csharp
   OcrInput scans = new OcrInput(InputType.PDF);
   scans.Add("Delivery-Agreement.pdf");
   ```
4. [Recognize](/ocr/net/recognition/) the text from document:
   ```csharp
   AsposeOcr api = new AsposeOcr();
   List<RecognitionResult> results = api.Recognize(scans);
   ```
5. Save the recognition result as a Microsoft Word (DOCX) format. We also enable automatic spelling error correction to further improve recognition accuracy.
   ```csharp
   AsposeOcr.SaveMultipageDocument("contract.docx", SaveFormat.Docx, results, true);
   ```

### Full code

```csharp
using Aspose.OCR;

namespace EditScan
{
	internal class Program
	{
		static void Main(string[] args)
		{
			// Apply license
			License license = new License();
			license.SetLicense("Aspose.OCR.lic");
			// Load the scanned agreement
			OcrInput scans = new OcrInput(InputType.PDF);
			scans.Add("Delivery-Agreement.pdf");
			// Recognize the text from document
			AsposeOcr api = new AsposeOcr();
			List<RecognitionResult> results = api.Recognize(scans);
			// Automatically correct spelling errors and save editable document in Microsoft Word (DOCX) format
			AsposeOcr.SaveMultipageDocument("contract.docx", SaveFormat.Docx, results, true);
			// Report progress
			Console.WriteLine($@"The scan has been converted to '{Directory.GetCurrentDirectory()}\contract.docx'.");
		}
	}
}
```

## Running

Run the program directly from the Visual Studio or build it and execute the file from the command line. Wait a few seconds, depending on your system performance.

A `contract.docx` file will be created in the program working directory. You can open it Microsoft Word, edit the content, search for text, and copy and paste the text to other documents.

## Learn more

- Specify the [recognition language](/ocr/net/languages/).
- Choose the [document structure detection algorithm](/ocr/net/areas-detection/) that best suits your specific content.
- Use the specialized recognition model for reading [invoices](/ocr/net/recognition/invoice/).
- Get recognition results as [plain text](/ocr/net/save-text/).
- Automatically [correct](/ocr/net/automatic-spelling-correction/) spelling errors.
