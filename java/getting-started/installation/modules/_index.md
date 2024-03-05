---
weight: 20
date: "2024-03-04"
author: "Vladimir Lapin"
type: docs
url: /java/modules/
feedback: OCRJAVA
title: Installing advanced OCR features
description: How to extend Aspose.OCR for Java functionality by adding downloadable modules to the project.
keywords:
- install
- update
- repository
- package
- advanced
- models
- extensions
---

Starting with Aspose.OCR for Java version **23.2.0**, the distributive offers basic recognition capabilities only. Additional features can be added via downloadable resources, freely available in our [online repository](https://github.com/aspose-ocr/resources).

This approach allows you to selectively choose which features you need for your project, keeping your application lean and modular. For example, if you only need Cyrillic characters recognition, you may omit Chinese, Hindi and other OCR models, saving significant amounts of disk space.

By default, Aspose.OCR for Java automatically downloads the required resources as needed, saving you time and effort in managing dependencies. You also have an option to [manually manage the resources](/ocr/java/modules/management/) for your project.

## Important considerations

If you choose to automatically download resources on demand, consider the following:

- The device hosting your application must have access to Internet or local repository.
- The application must be allowed outbound HTTP access to the resource repository's URL and port in the firewall.
- Depending on your Internet connection's speed, the automatic download of resources may take some time. This will result in increased processing time when you first call a method that depends on the downloaded resource.

If the above-mentioned constraints are not feasible, consider using Aspose.OCR for Java library in [offline mode](/ocr/java/modules/offline/).
