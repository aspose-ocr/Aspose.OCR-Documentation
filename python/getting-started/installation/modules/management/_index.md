---
weight: 10
date: "2024-05-30"
author: "Vladimir Lapin"
type: docs
url: /python-net/modules/management/
feedback: OCRPYNET
title: Managing downloadable resources
description: How to manage Aspose.OCR for Python via .NET downloadable modules.
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

By default, Aspose.OCR for Python via .NET automatically downloads the required resources when you call the method which depends on them.

{{% alert color="caution" %}} 
Depending on your Internet connection's speed, the automatic download of resources may take some time. This will result in increased processing time when you first call a method that depends on the downloaded resource.
{{% /alert %}}

Out of the box, the library is preconfigured to use the Aspose.OCR [resource repository](https://github.com/aspose-ocr/resources). The resources will be downloaded into the _aspose_data_ folder in the application’s working directory; if the folder is missing, it is automatically created. No configuration is required.

However, you have an option to manually manage the resources for your project using the methods of `Resources` class.

## Setting up the repository

To return the URL of the online repository from which Aspose.OCR for Python via .NET resources are downloaded, use `Resources.get_repository()` method. By default, the resources are downloaded from https://github.com/aspose-ocr/resources/; however, you can use your own repository or even Internet or intranet web site:

1. Copy the entire content of the **main** branch: https://github.com/aspose-ocr/resources/tree/main. You can use any of the following options:

    - Using Git command: `git clone git@github.com:aspose-ocr/resources.git`
    - [Download](https://github.com/aspose-ocr/resources/archive/refs/heads/main.zip) and unpack the ZIP archive.

2. Publish _all_ downloaded files to your own HTTP resource. The resource must be must be freely accessible to the application without providing credentials; Aspose.OCR for Python via .NET does not support authentication. You may use:

    - Public GitHub repository.
    - Private GitLab.
    - A folder on a web site.

3. Provide a link to `Resources.set_repository()` method. Depending on the resource, use the following links:

    - A link to the root directory of the branch in a public GitHub repository in form `https://github.com/{project}/{repository}/blob/{branch}/`. For example, `Resources.set_repository("https://github.com/aspose-ocr/resources/blob/main")`.
    - A link to GitLab raw files in form `https://{domain}/{project}/{repository}/-/raw/{branch}/`. For example, `Resources.set_repository("https://aspose.com/ocr/resources/-/raw/master/")`.
    - A link to the directory on a web site (either intranet or public). For example `Resources.set_repository("http://localhost/aspose-ocr-resources/")`.

## Specifying the local folder

To specify an absolute or relative path to the folder where the resources will be downloaded, use `Resources.set_local_path()` method. Pass `false` to the `create` parameter to prevent the directory from being created automatically. For example: `Resources.set_local_path("aspose/ocr", false)`

To get the full path where the resources will be downloaded, use `Resources.get_local_path()` method. By default, the resources are downloaded into the _aspose_data_ folder in the application’s working directory.

## Downloading the resources

To get the full list of compatible resources from the online repository, use `Resources.list_remote()` method. To find more information on a specific resource, refer to the following [link](https://github.com/aspose-ocr/resources/blob/main/README.md#resources).

There are several ways to download the resources:

Option | Method | Benefits | Drawbacks
------ | ------ | -------- | ---------
Automatically download the resource when you call the method which depends on it. | _n/a_ | <ul><li>Default behavior which requires no coding.</li></ul> | <ul><li>Increased processing time when you first call a method that depends on the downloaded resource.</li></ul>
Download all resources at once. | `Resources.fetch_all()` | <ul><li>No further delays during the application's lifetime.</li></ul> | <ul><li>Downloading all resource files may take a long time.</li><li>Unnecessary (unused) resources will consume network traffic and disk space.</li></ul>
Download a specific resource by name. | `Resources.fetch_resource()` | <ul><li>No further delays during the application's lifetime.</li><li>You only download and store what is necessary.</li></ul> | <ul><li>You have to manually maintain the required resources.</li></ul>
Bulk download of resources by names. | `Resources.fetch_resources()` | <ul><li>No further delays during the application's lifetime.</li><li>You only download and store what is necessary.</li></ul> | <ul><li>You have to manually maintain the required resources.</li></ul>

{{% alert color="primary" %}} 
If you manually download the resources which already exist in the local folder, they will be overwritten.
{{% /alert %}}

To prevent the resources from being automatically downloaded, use `Resources.allow_automatic_downloads(false)` method. This will not affect the manual downloads.

## Managing the resources

To get the list of Aspose.OCR resources stored in the local folder, use `Resources.list_local()` method. The resource names are returned as a string array.

To delete a locally stored resource, use `Resources.remove_local()` method or simply remove the corresponding file.

## Example

The code sample below illustrates how to manually install Cyrillic recognition model:

```python
# Download Cyrillic OCR model to "aspose/ocr" directory in the application working directory
Resources.set_local_path("aspose/ocr")
Resources.fetch_resource("aspose-ocr-cyrillic-v1");
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Recognize Ukrainian text
recognitionSettings = RecognitionSettings()
recognitionSettings.language = Language.UKR
# Recognize the image
result = api.recognize(input, recognitionSettings)
# Print recognition result
print(result[0].recognition_text)
input("Press Enter to continue...")
```
