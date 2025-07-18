---
weight: 20
date: "2023-09-02"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/logging/
feedback: OCRPYNET
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

Aspose.OCR for Python via .NET can show recognition progress in the console or log it to a file. The logging is activated with a static [`Logging`](https://reference.aspose.com/ocr/python-net/aspose.ocr/logging/) class. You can use the following properties to activate logging and specify its parameters:

Property | Description
-------- | -----------
`console` | Set to `true` to enable the display of recognition progress in the console.
`file_system` | Set to `true` to write recognition progress to a file specified in `log_file_path` property.
`log_file_path` | Specify an absolute or relative path to the log file. Applicable only when the `file_system` property is set to `true`.
`logging_level` | Specify the log severity. See **Log severity levels** for details.

{{< tabs tabID="1" tabTotal="2" tabName1="Enable logging" tabName2="Log" >}}
{{< tab tabNum="1" >}}
```python
Logging.console = true;
Logging.file_system = true;
Logging.log_file_path = "recognition.log";
Logging.logging_level = LoggingLevel.DEBUG;
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

You can configure the log severity by specifying one of the following values in `logging_level` property:

Severity | Value | Description
-------- | ----- | -----------
`LoggingLevel.ERROR` | 2 | Error events of considerable importance that will affect normal program execution.
`LoggingLevel.WARNING` | 1 | Potentially harmful situations that might still allow the application to continue running.
`LoggingLevel.DEBUG` | 0 | Detailed trace messages useful for application developers.
`LoggingLevel.NONE` | 3 | No logging. Works the same as turning off logging with `console` and `file_system` parameters.
