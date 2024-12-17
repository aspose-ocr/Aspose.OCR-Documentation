---
weight: 30
date: "2023-01-23"
author: "Vladimir Lapin"
type: docs
url: /net/logging/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
title: Logging recognition events
description: How to output recognition events to the console or write them to a file.
keywords:
- track
- log
- information
- error
- debug
- severity
---

Aspose.OCR for .NET can show recognition progress in the console or log it to a file. The logging is activated with a static [`Aspose.OCR.Logging`](https://reference.aspose.com/ocr/net/aspose.ocr/logging/) class. You can use the following properties to activate logging and specify its parameters:

Property | Type | Description
-------- | ---- | -----------
`Aspose.OCR.Logging.Console` | `bool` | Set to `true` to enable the display of recognition progress in the console.
`Aspose.OCR.Logging.FileSystem` | `bool` | Set to `true` to write recognition progress to a file specified in `Aspose.OCR.Logging.LogFilePath` property.
`Aspose.OCR.Logging.LogFilePath` | `string` | Specify an absolute or relative path to the log file. Applicable only when the `Aspose.OCR.Logging.FileSystem` property is set to `true`.
`Aspose.OCR.Logging.LoggingLevel` | `Aspose.OCR.LoggingLevel` | Specify the log severity. See **Log severity levels** for details.

{{< tabs tabID="1" tabTotal="2" tabName1="Enable logging" tabName2="Log" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.Logging.Console = true;
Aspose.OCR.Logging.FileSystem = true;
Aspose.OCR.Logging.LogFilePath = "recognition.log";
Aspose.OCR.Logging.LoggingLevel = LoggingLevel.Debug;
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```log
Open file. Started. 11.01.2023 12:32:58
Open file. Ended. 11.01.2023 12:32:59
Read image data. Started. 11.01.2023 12:32:59
Read image data. Ended. 11.01.2023 12:32:59
Preprocess file. Started. 11.01.2023 12:32:59
Preprocess file. Ended. 11.01.2023 12:33:00
Recognition process. Started. 11.01.2023 12:33:01
Region detection. Started. 11.01.2023 12:33:01
Region detection. Ended. 11.01.2023 12:33:10
Recognize characters. Started. 11.01.2023 12:33:10
Recognize characters. Ended. 11.01.2023 12:33:11
Recognition process. Ended. 11.01.2023 12:33:11
```
{{< /tab >}}
{{< /tabs >}}

## Log severity levels

You can configure the log severity by specifying one of the following values in `Aspose.OCR.Logging.LoggingLevel` property:

Severity | Value | Description
-------- | ----- | -----------
`Aspose.OCR.LoggingLevel.Error` | 2 | Error events of considerable importance that will affect normal program execution.
`Aspose.OCR.LoggingLevel.Warning` | 1 | Potentially harmful situations that might still allow the application to continue running.
`Aspose.OCR.LoggingLevel.Debug` | 0 | Detailed trace messages useful for application developers.
`Aspose.OCR.LoggingLevel.None` | 3 | No logging. Works the same as turning off logging with `Aspose.OCR.Logging.Console` and `Aspose.OCR.Logging.FileSystem` parameters.
