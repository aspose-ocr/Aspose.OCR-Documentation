---
weight: 20
date: "2024-03-15"
author: "Vladimir Lapin"
type: docs
url: /java/languages/
feedback: OCRJAVA
aliases:
- /java/working-with-different-languages/
title: Recognition languages
description: How to specify the language that is used by the Aspose.OCR recognition engine.
keywords:
- language
- locale
- characters
- country
---

{{% alert color="caution" %}} 
To recognize text in certain languages, you must [install](/ocr/java/modules/) additional recognition models:

- Cyrillic text recognition: **aspose-ocr-cyrillic-v1**
- Chinese text recognition: **aspose-ocr-chinese-v1**
- Hindi text recognition: **aspose-ocr-hindi-v1**
{{% /alert %}}

Aspose.OCR for Java can recognize a text in a large number of languages and all popular writing scripts, including texts with mixed languages.

To specify a language for recognition, provide one of the following values in [`setLanguage`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setLanguage-com.Language-) method of [RecognitionSettings](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings) class:

Value | Alphabet
----- | --------
`Language.ExtLatin` | Auto-detect [all supported Latin characters](/ocr/net/supported-characters/#extended-latin) and diacritics
`Language.Cyrillic` | All supported Cyrillic characters (auto-detect)
`Language.Afr` | Afrikaans
`Language.Aln` | Albanian
`Language.Awa` | Awadhi
`Language.Azb` | Azerbaijani (Azeri)
`Language.Bcl` | Bikol
`Language.Bel` | Belarusan (Belorussian)
`Language.Bem` | Bemba (Chibemba)
`Language.Bew` | Betawi
`Language.Bgc` | Haryanvi
`Language.Bho` | Bhojpuri
`Language.Bhr` | Malagasy
`Language.Bjj` | Kanauji
`Language.Bos` | Bosnian
`Language.Bul` | Bulgarian
`Language.Cat` | Catalan
`Language.Ccx` | Zhuang
`Language.Cdo` | Min Dong
`Language.Ceb` | Cebuano
`Language.Ces` | Czech
`Language.Che` | Chechen
`Language.Cmn` | Mandarin (Chinese)
`Language.Cpx` | Pu-Xian
`Language.Dan` | Danish
`Language.Deu` | German
`Language.Dhd` | Dhundari
`Language.Diq` | Dimli
`Language.Doc` | Dong
`Language.Eng` | English
`Language.Est` | Estonian
`Language.Fin` | Finnish
`Language.Fra` | French
`Language.Gan` | Gan
`Language.Gax` | Oromo
`Language.Gbm` | Garhwali
`Language.Glg` | Galician
`Language.Glk` | Gilaki
`Language.Guz` | Gusii
`Language.Hak` | Hakka
`Language.Hau` | Hausa
`Language.Hbs` | Serbo-Croatian (Latin)
`Language.Hil` | Hiligaynon
`Language.Hin` | Hindi
`Language.Hmn` | Hmong
`Language.Hne` | Chattisgarhi (Laria, Khaltahi)
`Language.Hrv` | Croatian
`Language.Hsn` | Xiang
`Language.Hun` | Hungarian (Magyar)
`Language.Ilo` | Ilocano
`Language.Ind` | Indonesian
`Language.Ita` | Italian
`Language.Kaz` | Kazakh
`Language.Kbd` | Kabardian
`Language.Kfy` | Kumauni
`Language.Kin` | Rwanda
`Language.Kln` | Nandi
`Language.Kmr` | Kurdish (Kurmanji)
`Language.Knc` | Kanuri
`Language.Knn` | Konkani
`Language.Kon` | Kikongo
`Language.Latin` | Latin
`Language.Lav` | Latvian
`Language.Lit` | Lithuanian
`Language.Lmn` | Lamani (Lambadi)
`Language.Lnc` | Occitan
`Language.Luo` | Luo
`Language.Mag` | Magahi
`Language.Mai` | Maithili
`Language.Mak` | Makassar (Makasar)
`Language.Mar` | Marathi
`Language.Mer` | Meru
`Language.Min` | Minangkabau
`Language.Mly` | Malay (Melayu)
`Language.Mnp` | Min Bei
`Language.Mtq` | Muong
`Language.Mtr` | Mewari
`Language.Mui` | Musi
`Language.Mup` | Malvi
`Language.Nan` | Min Nan
`Language.Nbl` | Ndebele
`Language.Nds` | Low German
`Language.Nep` | Nepali
`Language.Nld` | Dutch
`Language.Nor` | Norwegian
`Language.Nso` | Sotho (Northern)
`Language.Nya` | Chichewa (Chewa, Nyanja)
`Language.Pag` | Pangasinan
`Language.Pam` | Kapampangan
`Language.Pcc` | Bouyei (Buyi, Giáy)
`Language.Plm` | Palembang
`Language.Pol` | Polish
`Language.Por` | Portuguese
`Language.Quc` | K'iche'
`Language.Qxa` | Quechua
`Language.Rjb` | Rajbanshi
`Language.Ron` | Romanian
`Language.Ruf` | Luguru
`Language.Rus` | Russian
`Language.Rwr` | Marwari
`Language.Sas` | Sasak
`Language.Slk` | Slovak
`Language.Slv` | Slovene (Slovenian)
`Language.Sna` | Shona (Karanga)
`Language.Som` | Somali
`Language.Sot` | Sotho (Southern)
`Language.Spa` | Spanish
`Language.Srp` | Serbian (Cyrillic)
`Language.Srr` | Serer-Sine
`Language.Ssw` | Swati (Swazi)
`Language.Suk` | Sukuma
`Language.Sun` | Sundanese (Sunda)
`Language.Swe` | Swedish
`Language.Swh` | Swahili
`Language.Tgl` | Tagalog (Pilipino)
`Language.Toi` | Tonga
`Language.Tsn` | Tswana
`Language.Tso` | Tsonga
`Language.Tuk` | Turkmen
`Language.Tum` | Tumbuka
`Language.Tur` | Turkish
`Language.Ukr` | Ukrainian
`Language.Umb` | Umbundu
`Language.Vie` | Vietnamese
`Language.Vmw` | Makua (Makhuwa)
`Language.Wal` | Wolaytta
`Language.War` | Waray-Waray
`Language.Wbr` | Wagdi
`Language.Wtm` | Mewati
`Language.Wuu` | Wu (Changzhou)
`Language.Xho` | Xhosa
`Language.Yao` | Yao
`Language.Yor` | Yoruba
`Language.Yue` | Cantonese
`Language.Zul` | Zulu

If this parameter is omitted, the OCR engine will assume that the text is written in extended Latin.

{{% alert color="primary" %}}
Make sure you specify the correct language for the image. If you try to recognize Cyrillic text using `Language.Eng`, only the characters that look the same in both languages (for example, `с` and `c`) will be correctly recognized. Other characters will be replaced with similar-looking alternatives.
{{% /alert %}}

## Example

The following code sample demonstrates how to specify the recognition language:

```java
AsposeOCR api = new AsposeOCR();
RecognitionSettings recognitionSettings = new RecognitionSettings();
// Recognize Ukrainian text
recognitionSettings.setLanguage(Language.Ukr);
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```
