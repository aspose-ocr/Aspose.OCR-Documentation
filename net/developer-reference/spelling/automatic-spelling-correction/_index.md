---
weight: 10
date: "2023-04-07"
author: "Vladimir Lapin"
type: docs
url: /net/automatic-spelling-correction/
feedback: OCRNET
aliases:
- /net/spelling-correction/
- /net/result-correction-with-spell-checking/
title: Automatic spelling correction
description: How to automatically find and correct spelling errors in recognition results.
keywords:
- spelling
- typo
- error
- fix
- replace
- correct
---

Aspose.OCR for .NET can automatically replace commonly misspelled words in recognition results with the correct ones. This functionality supports the following languages:

Value | Language
----- | --------
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Cze` | Czech
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Dan` | Danish
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Deu` | German
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Dum` | Dutch
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Eng` | English
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Est` | Estonian
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Fin` | Finnish
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Fra` | French
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Ita` | Italian
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Lav` | Latvian
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Lit` | Lithuanian
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Pol` | Polish
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Por` | Portuguese
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Rum` | Romanian
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Slk` | Slovak
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Slv` | Slovene
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Spa` | Spanish
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Swe` | Swedish

Spell checking is done on the fly, either on [output](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/getspellcheckcorrectedtext/) or on [saving](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/save/) the results:

{{< tabs tabID="1" tabTotal="2" tabName1="Output corrected results" tabName2="Save corrected results" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input);
// Output corrected result
string correctedResult = results[0].GetSpellCheckCorrectedText(Aspose.OCR.SpellChecker.SpellCheckLanguage.Eng);
Console.WriteLine(correctedResult);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input);
// Save corrected result
results[0].Save("result.txt", Aspose.OCR.SaveFormat.Text, true, Aspose.OCR.SpellChecker.SpellCheckLanguage.Deu);
```
{{< /tab >}}
{{< /tabs >}}

{{% alert color="primary" %}}
Automatic spelling correction requires additional processing resources and is disabled by default.
{{% /alert %}}

## Spelling correction of any text

You can also correct misspelled words in any text string using [`CorrectSpelling`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/correctspelling/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class:

```csharp
string text = "Die schönste Jungfrau sitzet dort oben wunderbar";
string correctedText = recognitionEngine.CorrectSpelling(text, Aspose.OCR.SpellChecker.SpellCheckLanguage.Deu);
Console.WriteLine(correctedResult);
```
