---
weight: 20
date: "2023-07-20"
author: "Vladimir Lapin"
type: docs
url: /cpp/logging/
feedback: OCRCPP
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

Aspose.OCR for C++ can show recognition progress in the console or log it to a file. The logging is activated with [`asposeocr_set_log_settings()`](https://reference.aspose.com/ocr/cpp/groupAspose#gad4bae7881db3432ae338c3cabadfbf77) function. You can specify the following logging parameters:

Property | Description
-------- | -----------
`console_output_enabled` | Set to `true` to enable the display of recognition progress in the console.
`logging_level` | Specify the log severity. See **Log severity levels** for details.
`output_path` | Specify an absolute or relative path to the log file.

## Log severity levels

You can configure the log severity by specifying one of the following values in `logging_level` property:

Severity | Description
-------- | -----------
`ASPOSE_OCR_LOG_ERROR` | Error events of considerable importance that will affect normal program execution.
`ASPOSE_OCR_LOG_WARNING` | Potentially harmful situations that might still allow the application to continue running. The log will also include errors (as if `ASPOSE_OCR_LOG_ERROR` is specified).
`ASPOSE_OCR_LOG_TRACE` | Detailed trace messages useful for application developers.  The log will also include errors and warnings (as if `ASPOSE_OCR_LOG_ERROR` and `ASPOSE_OCR_LOG_WARNING` are specified).

## Example

```cpp
AsposeOCRLogSettings log_settings;
log_settings.console_output_enabled = false;
log_settings.logging_level = ASPOSE_OCR_LOG_ERROR;
log_settings.output_path = "errors.log";
asposeocr_set_log_settings(log_settings);
```
