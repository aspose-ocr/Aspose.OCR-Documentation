---
weight: 10
date: "2023-11-24"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/system-requirements/
title: System requirements
description: Minimum requirements and prerequisites for web applications built with Aspose.OCR for JavaScript via C++.
keywords:
- prerequisites
- requirements
- framework
- environment
- web
- javascript
---

Aspose.OCR for JavaScript via C++ is based on [WebAssembly (Wasm)](https://webassembly.org/) technology, which allows the code to run directly in the end user's web browser (client-side) or in browser-based environments.

## Web browsers

The following browsers are supported:

- Google Chrome 57 and above;
- Microsoft Edge 16 and above;
- Mozilla Firefox 53 and above;
- Opera 44 and above;
- Safari 11 and above;
- Google Chrome for Android 119 and above;
- Firefox for Android 119 and above;
- Samsung Internet 7.2 and above;
- Opera Mobile 73 and above.

{{% alert color="primary" %}}
Aspose.OCR for JavaScript via C++ library can also work on other browsers supporting Wasm technology, but each case should be tested individually.
{{% /alert %}}

Regardless of your browser, we highly recommend updating to the latest version to ensure maximum performance and stability.

### Working with local files

Most web browsers have very strict CORS policies that prevent them from accessing files from local storage. As a result, you may get "_Access to XMLHttpRequest at 'file:///.../asposeocr.data' from origin 'null' has been blocked by CORS policy_" error when trying to open an HTML page directly from the disk.

You can either disable cross-origin restrictions (see your specific browser's documentation for instructions) or open the page over HTTP using any web server, for example the one built into Python:

```bash
python -m http.server 8080
```

## Electron

In addition to browsers, the library can work in [Electron](https://www.electronjs.org/) cross-platform desktop apps.

You can use Electron version 3 and above.
