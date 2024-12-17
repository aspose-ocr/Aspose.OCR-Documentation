---
weight: 30
date: "2024-11-21"
author: "Vladimir Lapin"
type: docs
url: /net/languages/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
aliases:
- /net/working-with-different-languages/
title: Recognition languages
description: How to specify the language that is used by the Aspose.OCR recognition engine.
keywords:
- language
- locale
- characters
- country
---

{{% alert color="caution" %}} 
To recognize text in certain languages, you must [install](/ocr/net/modules/) additional recognition models:


- Cyrillic text recognition: **aspose-ocr-cyrillic-v1**
- Chinese text recognition: **aspose-ocr-chinese-v2**
- Indic (Devanagari) text recognition: **aspose-ocr-hindi-v2**
- Arabic text recognition: **aspose-ocr-arabic-v1**
- Persian (Farsi) text recognition: **aspose-ocr-arabic-v1**
- Uyghur text recognition: **aspose-ocr-arabic-v1**
- Urdu text recognition: **aspose-ocr-arabic-v1**
- Japanese text recognition: **aspose-ocr-japanese-v1**
- Korean text recognition: **aspose-ocr-korean-v1**
- Kannada text recognition: **aspose-ocr-kannada-v1**
- Tamil text recognition: **aspose-ocr-tamil-v1**
- Telugu text recognition: **aspose-ocr-telugu-v1**
- Mixed-language Cyrillic/English recognition: **aaspose-ocr-cyrillic-v2**
- Mongolian text recognition: **aspose-ocr-cyrillic-v1**
{{% /alert %}}

Aspose.OCR for .NET can recognize a text in a large number of languages and all popular writing scripts, including texts with mixed languages.

To specify a language for recognition, provide one of the following values in [`Language`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/language/) property of [recognition settings](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/):

{{% alert color="primary" %}}
Mixed-language Cyrillic/English text recognition is experimental. If you are absolutely sure about the text language (for example, Ukrainian), it is recommended to specify the language directly.
{{% /alert %}}

Value | Alphabet
----- | --------
`Aspose.OCR.Language.ExtLatin` | Auto-detect [all supported Latin characters](/ocr/net/supported-characters/#extended-latin) and diacritics
`Aspose.OCR.Language.Cyrillic` | Auto-detect [all supported Cyrillic characters](/ocr/net/supported-characters/#cyrillic)
`Aspose.OCR.Language.Chinese` | All Chinese languages. Mixed-language Chinese/English texts also supported.
`Aspose.OCR.Language.Devanagari`<br />`Aspose.OCR.Language.Indic` | Indic texts based on Devanagari script, including mixed Devanagari/English texts.
`Aspose.OCR.Language.European` | Mixed-language Cyrillic/English texts (_experimental_).
`Aspose.OCR.Language.Afr` | Afrikaans
`Aspose.OCR.Language.Aln` | Albanian
`Aspose.OCR.Language.Ara` | Arabic (mixed texts in Arabic and English are also supported)
`Aspose.OCR.Language.Awa` | Awadhi
`Aspose.OCR.Language.Azb` | Azerbaijani (Azeri)
`Aspose.OCR.Language.Bcl` | Bikol
`Aspose.OCR.Language.Bel` | Belarusan (Belorussian)
`Aspose.OCR.Language.Bem` | Bemba (Chibemba)
`Aspose.OCR.Language.Bew` | Betawi
`Aspose.OCR.Language.Bgc` | Haryanvi
`Aspose.OCR.Language.Bho` | Bhojpuri
`Aspose.OCR.Language.Bhr` | Malagasy
`Aspose.OCR.Language.Bjj` | Kanauji
`Aspose.OCR.Language.Bos` | Bosnian
`Aspose.OCR.Language.Bul` | Bulgarian
`Aspose.OCR.Language.Cat` | Catalan
`Aspose.OCR.Language.Ccx` | Zhuang
`Aspose.OCR.Language.Cdo` | Min Dong
`Aspose.OCR.Language.Ceb` | Cebuano
`Aspose.OCR.Language.Ces` | Czech
`Aspose.OCR.Language.Che` | Chechen
`Aspose.OCR.Language.Cmn` | Mandarin (Chinese)
`Aspose.OCR.Language.Cpx` | Pu-Xian
`Aspose.OCR.Language.Dan` | Danish
`Aspose.OCR.Language.Deu` | German
`Aspose.OCR.Language.Dhd` | Dhundari
`Aspose.OCR.Language.Diq` | Dimli
`Aspose.OCR.Language.Doc` | Dong
`Aspose.OCR.Language.Eng` | English
`Aspose.OCR.Language.Est` | Estonian
`Aspose.OCR.Language.Fin` | Finnish
`Aspose.OCR.Language.Fra` | French
`Aspose.OCR.Language.Gan` | Gan
`Aspose.OCR.Language.Gax` | Oromo
`Aspose.OCR.Language.Gbm` | Garhwali
`Aspose.OCR.Language.Glg` | Galician
`Aspose.OCR.Language.Glk` | Gilaki
`Aspose.OCR.Language.Guz` | Gusii
`Aspose.OCR.Language.Hak` | Hakka
`Aspose.OCR.Language.Hau` | Hausa
`Aspose.OCR.Language.Hbs` | Serbo-Croatian (Latin)
`Aspose.OCR.Language.Hil` | Hiligaynon
`Aspose.OCR.Language.Hin` | Hindi
`Aspose.OCR.Language.Hmn` | Hmong
`Aspose.OCR.Language.Hne` | Chattisgarhi (Laria, Khaltahi)
`Aspose.OCR.Language.Hrv` | Croatian
`Aspose.OCR.Language.Hsn` | Xiang
`Aspose.OCR.Language.Hun` | Hungarian (Magyar)
`Aspose.OCR.Language.Ilo` | Ilocano
`Aspose.OCR.Language.Ind` | Indonesian
`Aspose.OCR.Language.Ita` | Italian
`Aspose.OCR.Language.Jpn` | Japanese (mixed texts in Japanese and English are also supported)
`Aspose.OCR.Language.Kan` | Mixed-language Kannada/English texts.
`Aspose.OCR.Language.Kaz` | Kazakh
`Aspose.OCR.Language.Kbd` | Kabardian
`Aspose.OCR.Language.Kfy` | Kumauni
`Aspose.OCR.Language.Kin` | Rwanda
`Aspose.OCR.Language.Kln` | Nandi
`Aspose.OCR.Language.Kmr` | Kurdish (Kurmanji)
`Aspose.OCR.Language.Knc` | Kanuri
`Aspose.OCR.Language.Knn` | Konkani
`Aspose.OCR.Language.Kon` | Kikongo
`Aspose.OCR.Language.Kor` | Korean (mixed texts in Korean and English are also supported)
`Aspose.OCR.Language.Latin` | Latin
`Aspose.OCR.Language.Lav` | Latvian
`Aspose.OCR.Language.Lit` | Lithuanian
`Aspose.OCR.Language.Lmn` | Lamani (Lambadi)
`Aspose.OCR.Language.Lnc` | Occitan
`Aspose.OCR.Language.Luo` | Luo
`Aspose.OCR.Language.Mag` | Magahi
`Aspose.OCR.Language.Mai` | Maithili
`Aspose.OCR.Language.Mak` | Makassar (Makasar)
`Aspose.OCR.Language.Mar` | Marathi
`Aspose.OCR.Language.Mer` | Meru
`Aspose.OCR.Language.Min` | Minangkabau
`Aspose.OCR.Language.Mly` | Malay (Melayu)
`Aspose.OCR.Language.Mnp` | Min Bei
`Aspose.OCR.Language.Mon` | Mongolian
`Aspose.OCR.Language.Mtq` | Muong
`Aspose.OCR.Language.Mtr` | Mewari
`Aspose.OCR.Language.Mui` | Musi
`Aspose.OCR.Language.Mup` | Malvi
`Aspose.OCR.Language.Nan` | Min Nan
`Aspose.OCR.Language.Nbl` | Ndebele
`Aspose.OCR.Language.Nds` | Low German
`Aspose.OCR.Language.Nep` | Nepali
`Aspose.OCR.Language.Nld` | Dutch
`Aspose.OCR.Language.Nor` | Norwegian
`Aspose.OCR.Language.Nso` | Sotho (Northern)
`Aspose.OCR.Language.Nya` | Chichewa (Chewa, Nyanja)
`Aspose.OCR.Language.Pag` | Pangasinan
`Aspose.OCR.Language.Pam` | Kapampangan
`Aspose.OCR.Language.Pcc` | Bouyei (Buyi, Giáy)
`Aspose.OCR.Language.Pes` | Persian (Farsi); mixed texts in Persian and English are also supported
`Aspose.OCR.Language.Plm` | Palembang
`Aspose.OCR.Language.Pol` | Polish
`Aspose.OCR.Language.Por` | Portuguese
`Aspose.OCR.Language.Quc` | K'iche'
`Aspose.OCR.Language.Qxa` | Quechua
`Aspose.OCR.Language.Rjb` | Rajbanshi
`Aspose.OCR.Language.Ron` | Romanian
`Aspose.OCR.Language.Ruf` | Luguru
`Aspose.OCR.Language.Rus` | Russian
`Aspose.OCR.Language.Rwr` | Marwari
`Aspose.OCR.Language.Sas` | Sasak
`Aspose.OCR.Language.Slk` | Slovak
`Aspose.OCR.Language.Slv` | Slovene (Slovenian)
`Aspose.OCR.Language.Sna` | Shona (Karanga)
`Aspose.OCR.Language.Som` | Somali
`Aspose.OCR.Language.Sot` | Sotho (Southern)
`Aspose.OCR.Language.Spa` | Spanish
`Aspose.OCR.Language.Srp` | Serbian (Cyrillic)
`Aspose.OCR.Language.Srr` | Serer-Sine
`Aspose.OCR.Language.Ssw` | Swati (Swazi)
`Aspose.OCR.Language.Suk` | Sukuma
`Aspose.OCR.Language.Sun` | Sundanese (Sunda)
`Aspose.OCR.Language.Swe` | Swedish
`Aspose.OCR.Language.Swh` | Swahili
`Aspose.OCR.Language.Tam` | Mixed-language Tamil/English texts.
`Aspose.OCR.Language.Tel` | Mixed-language Telugu/English texts.
`Aspose.OCR.Language.Tgl` | Tagalog (Pilipino)
`Aspose.OCR.Language.Toi` | Tonga
`Aspose.OCR.Language.Tsn` | Tswana
`Aspose.OCR.Language.Tso` | Tsonga
`Aspose.OCR.Language.Tuk` | Turkmen
`Aspose.OCR.Language.Tum` | Tumbuka
`Aspose.OCR.Language.Tur` | Turkish
`Aspose.OCR.Language.Uig` | Uyghur; mixed texts in Uyghur and English are also supported
`Aspose.OCR.Language.Ukr` | Ukrainian
`Aspose.OCR.Language.Umb` | Umbundu
`Aspose.OCR.Language.Urd` | Urdu; mixed texts in Urdu and English are also supported
`Aspose.OCR.Language.Vie` | Vietnamese
`Aspose.OCR.Language.Vmw` | Makua (Makhuwa)
`Aspose.OCR.Language.Wal` | Wolaytta
`Aspose.OCR.Language.War` | Waray-Waray
`Aspose.OCR.Language.Wbr` | Wagdi
`Aspose.OCR.Language.Wtm` | Mewati
`Aspose.OCR.Language.Wuu` | Wu (Changzhou)
`Aspose.OCR.Language.Xho` | Xhosa
`Aspose.OCR.Language.Yao` | Yao
`Aspose.OCR.Language.Yor` | Yoruba
`Aspose.OCR.Language.Yue` | Cantonese
`Aspose.OCR.Language.Zul` | Zulu

If this parameter is omitted, the OCR engine will assume that the text is written in extended Latin.

{{% alert color="primary" %}}
Make sure you specify the correct language for the image. If you try to recognize Cyrillic text using `Aspose.OCR.Language.Eng`, only the characters that look the same in both languages (for example, `с` and `c`) will be correctly recognized. Other characters will be replaced with similar-looking alternatives.
{{% /alert %}}

## Example

The following code sample demonstrates how to specify the recognition language:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Recognize Ukrainian text
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
