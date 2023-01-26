---
weight: 110
date: "2023-01-26"
author: "Vladimir Lapin"
type: docs
url: /java/logging/
feedback: OCRJAVA
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

Aspose.OCR for Java can show recognition progress in the console or log it to a file. The logging is activated and configured with a static [`Logging`](https://reference.aspose.com/ocr/java/com.aspose.ocr/Logging) class. You can use the following properties to activate logging and specify its parameters:

Property | Type | Description
-------- | ---- | -----------
`Logging.console` | `bool` | Set to `true` to enable the display of recognition progress in the console.
`Logging.fileSystem` | `bool` | Set to `true` to write recognition progress to a file specified in `Logging.logFilePath` property.
`Logging.logFilePath` | `string` | Specify an absolute or relative path to the log file. Applicable only when the `Logging.fileSystem` property is set to `true`.
`Logging.loggingLevel` | `LoggingLevel` | Specify the log severity. See **Log severity levels** for details.

{{< tabs tabID="1" tabTotal="2" tabName1="Enable logging" tabName2="Result" >}}
{{< tab tabNum="1" >}}
```java
Logging.loggingLevel = LoggingLevel.Debug;
Logging.fileSystem = true;
Logging.console = true;
Logging.logFilePath = "recognition.log";
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

You can configure the log severity by specifying one of the following values in `Logging.loggingLevel` property:

Severity | Value | Description
-------- | ----- | -----------
`LoggingLevel.Error` | 2 | Error events of considerable importance that will affect normal program execution.
`LoggingLevel.Warning` | 1 | Potentially harmful situations that might still allow the application to continue running.
`LoggingLevel.Debug` | 0 | Detailed trace messages useful for application developers.
`LoggingLevel.None` | 3 | No logging. Works the same as turning off logging with `Logging.console` and `Logging.fileSystem` parameters.
