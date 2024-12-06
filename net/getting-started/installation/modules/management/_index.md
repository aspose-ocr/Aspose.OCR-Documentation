---
weight: 10
date: "2024-02-27"
author: "Vladimir Lapin"
type: docs
url: /net/modules/management/
feedback: OCRNET
title: Managing downloadable resources
description: How to manage Aspose.OCR for .NET downloadable modules.
keywords:
- install
- update
- repository
- package
- advanced
- models
- extensions
- online
---

By default, Aspose.OCR for .NET automatically downloads the required resources when you call the method which depends on them.

{{% alert color="caution" %}} 
Depending on your Internet connection's speed, the automatic download of resources may take some time. This will result in increased processing time when you first call a method that depends on the downloaded resource.
{{% /alert %}}

Out of the box, the library is preconfigured to use the Aspose.OCR [resource repository](https://github.com/aspose-ocr/resources). The resources will be downloaded into the _aspose_data_ folder in the application’s working directory; if the folder is missing, it is automatically created. No configuration is required.

However, you have an option to manually manage the resources for your project using the static methods of `Aspose.OCR.Resources` class.

## Setting up the repository

To return the URL of the online repository from which Aspose.OCR for .NET resources are downloaded, use `Aspose.OCR.Resources.GetRepository()` method. By default, the resources are downloaded from https://github.com/aspose-ocr/resources/; however, you can use your own repository or even Internet or intranet web site:

1. Copy the entire content of the **main** branch: https://github.com/aspose-ocr/resources/tree/main. You can use any of the following options:

    - Using Git command: `git clone git@github.com:aspose-ocr/resources.git`
    - [Download](https://github.com/aspose-ocr/resources/archive/refs/heads/main.zip) and unpack the ZIP archive.

2. Publish _all_ downloaded files to your own HTTP resource. The resource must be must be freely accessible to the application without providing credentials; Aspose.OCR for .NET does not support authentication. You may use:

    - Public GitHub repository.
    - Private GitLab.
    - A folder on a web site.

3. Provide a link to `Aspose.OCR.Resources.SetRepository()` method. Depending on the resource, use the following links:

    - A link to the root directory of the branch in a public GitHub repository in form `https://github.com/{project}/{repository}/blob/{branch}/`. For example, `Aspose.OCR.Resources.SetRepository("https://github.com/aspose-ocr/resources/blob/main");`.
    - A link to GitLab raw files in form `https://{domain}/{project}/{repository}/-/raw/{branch}/`. For example, `Aspose.OCR.Resources.SetRepository("https://aspose.com/ocr/resources/-/raw/master/");`.
    - A link to the directory on a web site (either intranet or public). For example `Aspose.OCR.Resources.SetRepository("http://localhost/aspose-ocr-resources/");`.

## Specifying the local folder

To specify an absolute or relative path to the folder where the resources will be downloaded, use `Aspose.OCR.Resources.SetLocalPath()` method. Pass `false` to the `create` parameter to prevent the directory from being created automatically. For example: `Aspose.OCR.Resources.SetLocalPath("aspose/ocr", false);`

To get the full path where the resources will be downloaded, use `Aspose.OCR.Resources.GetLocalPath()` method. By default, the resources are downloaded into the _aspose_data_ folder in the application’s working directory.

## Downloading the resources

To get the full list of compatible resources from the online repository, use `Aspose.OCR.Resources.ListRemote()` method. To find more information on a specific resource, refer to the following [link](https://github.com/aspose-ocr/resources/blob/main/README.md#resources).

There are several ways to download the resources:

Option | Method | Benefits | Drawbacks
------ | ------ | -------- | ---------
Automatically download the resource when you call the method which depends on it. | _n/a_ | <ul><li>Default behavior which requires no coding.</li></ul> | <ul><li>Increased processing time when you first call a method that depends on the downloaded resource.</li></ul>
Download all resources at once. | `Aspose.OCR.Resources.FetchAll()` | <ul><li>No further delays during the application's lifetime.</li></ul> | <ul><li>Downloading all resource files may take a long time.</li><li>Unnecessary (unused) resources will consume network traffic and disk space.</li></ul>
Download a specific resource by name. | `Aspose.OCR.Resources.FetchResource()` | <ul><li>No further delays during the application's lifetime.</li><li>You only download and store what is necessary.</li></ul> | <ul><li>You have to manually maintain the required resources.</li></ul>
Bulk download of resources by names. | `Aspose.OCR.Resources.FetchResources()` | <ul><li>No further delays during the application's lifetime.</li><li>You only download and store what is necessary.</li></ul> | <ul><li>You have to manually maintain the required resources.</li></ul>

{{% alert color="primary" %}} 
If you manually download the resources which already exist in the local folder, they will be overwritten.
{{% /alert %}}

To prevent the resources from being automatically downloaded, use `Aspose.OCR.Resources.AllowAutomaticDownloads(false)` method. This will not affect the manual downloads.

## Managing the resources

To get the list of Aspose.OCR resources stored in the local folder, use `Aspose.OCR.Resources.ListLocal()` method. The resource names are returned as a string array.

To delete a locally stored resource, use `Aspose.OCR.Resources.RemoveLocal()` method or simply remove the corresponding file.

## Example

The code sample below illustrates how to manually install Cyrillic recognition model:

```csharp
// Download Cyrillic OCR model to "aspose/ocr" directory in the application working directory
Aspose.OCR.Resources.SetLocalPath("aspose/ocr");
Aspose.OCR.Resources.FetchResource("aspose-ocr-cyrillic-v1");
// Initialize Aspose.OCR for .NET recognition API
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source1.png");
input.Add("source2.jpg");
// Set recognition language
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
    Console.WriteLine(result.RecognitionText);
}
```
