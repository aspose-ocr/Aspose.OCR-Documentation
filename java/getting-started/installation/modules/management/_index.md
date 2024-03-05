---
weight: 10
date: "2024-03-04"
author: "Vladimir Lapin"
type: docs
url: /java/modules/management/
feedback: OCRJAVA
title: Managing downloadable resources
description: How to manage Aspose.OCR for Java downloadable modules.
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

By default, Aspose.OCR for Java automatically downloads the required resources when you call the method which depends on them.

{{% alert color="caution" %}} 
Depending on your Internet connection's speed, the automatic download of resources may take some time. This will result in increased processing time when you first call a method that depends on the downloaded resource.
{{% /alert %}}

Out of the box, the library is preconfigured to use the Aspose.OCR [resource repository](https://github.com/aspose-ocr/resources). The resources will be downloaded into the _aspose_data_ directory in the application’s working directory; if the directory is missing, it is automatically created. No configuration is required.

However, you have an option to manually manage the resources for your project.

## Setting up the repository

To return the URL of the online repository from which Aspose.OCR for Java resources are downloaded, use `Resources.GetRepository()` method. By default, the resources are downloaded from https://github.com/aspose-ocr/resources/; however, you can use your own repository or even Internet or intranet web site:

1. Copy the entire content of the **main** branch: https://github.com/aspose-ocr/resources/tree/main. You can use any of the following options:

    - Using Git command: `git clone git@github.com:aspose-ocr/resources.git`
    - [Download](https://github.com/aspose-ocr/resources/archive/refs/heads/main.zip) and unpack the ZIP archive.

2. Publish _all_ downloaded files to your own HTTP resource. The resource must be must be freely accessible to the application without providing credentials; Aspose.OCR for Java does not support authentication. You may use:

    - Public GitHub repository.
    - Private GitLab.
    - A directory on a web site.

3. Provide a link to `Resources.SetRepository()` method. Depending on the resource, use the following links:

    - A link to the root directory of the branch in a public GitHub repository in form `https://github.com/{project}/{repository}/blob/{branch}/`. For example, `Resources.SetRepository("https://github.com/aspose-ocr/resources/blob/main");`.
    - A link to GitLab raw files in form `https://{domain}/{project}/{repository}/-/raw/{branch}/`. For example, `Resources.SetRepository("https://aspose.com/ocr/resources/-/raw/master/");`.
    - A link to the directory on a web site (either intranet or public). For example `Resources.SetRepository("http://localhost/aspose-ocr-resources/");`.

## Specifying the local directory

To specify an absolute or relative path to the directory where the resources will be downloaded, use `Resources.SetLocalPath()` method. Pass `false` to the `create` parameter to prevent the directory from being created automatically. For example: `Resources.SetLocalPath("aspose/ocr", false);`

To get the full path where the resources will be downloaded, use `Resources.GetLocalPath()` method. By default, the resources are downloaded into the _aspose_data_ directory in the application’s working directory.

## Downloading the resources

To get the full list of compatible resources from the online repository, use `Resources.ListRemote()` method. To find more information on a specific resource, refer to the following [link](https://github.com/aspose-ocr/resources/blob/main/README.md#resources).

There are several ways to download the resources:

Option | Method | Benefits | Drawbacks
------ | ------ | -------- | ---------
Automatically download the resource when you call the method which depends on it. | _n/a_ | <ul><li>Default behavior which requires no coding.</li></ul> | <ul><li>Increased processing time when you first call a method that depends on the downloaded resource.</li></ul>
Download all resources at once. | `Resources.FetchAll()` | <ul><li>No further delays during the application's lifetime.</li></ul> | <ul><li>Downloading all resource files may take a long time.</li><li>Unnecessary (unused) resources will consume network traffic and disk space.</li></ul>
Download a specific resource by name. | `Resources.FetchResource()` | <ul><li>No further delays during the application's lifetime.</li><li>You only download and store what is necessary.</li></ul> | <ul><li>You have to manually maintain the required resources.</li></ul>
Bulk download of resources by names. | `Resources.FetchResources()` | <ul><li>No further delays during the application's lifetime.</li><li>You only download and store what is necessary.</li></ul> | <ul><li>You have to manually maintain the required resources.</li></ul>

{{% alert color="primary" %}} 
If you manually download the resources which already exist in the local directory, they will be overwritten.
{{% /alert %}}

To prevent the resources from being automatically downloaded, use `Resources.AllowAutomaticDownloads(false)` method. This will not affect the manual downloads.

## Managing the resources

To get the list of Aspose.OCR resources stored in the local directory, use `Resources.ListLocal()` method. The resource names are returned as a string array.

To delete a locally stored resource, use `Resources.RemoveLocal()` method or simply remove the corresponding file.

## Example

The code sample below illustrates how to manually install Hindi recognition model:

```java
// Download Hindi OCR model to "aspose/ocr" directory in the application working directory
Resources.SetLocalPath("aspose/ocr");
Resources.FetchResource("aspose-ocr-hindi-v1");
// Initialize Aspose.OCR recognition API
AsposeOCR api = new AsposeOCR();
RecognitionSettings recognitionSettings = new RecognitionSettings();
// Add image to the recognition batch
OcrInput source = new OcrInput(InputType.SingleImage);
source.add("image.png");
// Extract text from image
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setLanguage(Language.Hin);
ArrayList<RecognitionResult> results = api.Recognize(source, recognitionSettings);
System.out.println(result[0].recognition_text);
```
