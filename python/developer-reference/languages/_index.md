---
weight: 30
date: "2024-11-21"
author: "Vladimir Lapin"
type: docs
url: /python-net/languages/
feedback: OCRPYNET
title: Recognition languages
description: How to specify the language that is used by the Aspose.OCR for Python via .NET recognition engine.
keywords:
- language
- locale
- characters
- country
---

{{% alert color="caution" %}} 
To recognize text in certain languages, you must [install](/ocr/python-net/modules/) additional recognition models:

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
{{% /alert %}}

Aspose.OCR for Python via .NET can recognize a text in a large number of languages and all popular writing scripts, including texts with mixed languages.

To specify a language for recognition, provide one of the following values in `language` property of recognition settings:

{{% alert color="primary" %}}
Mixed-language Cyrillic/English text recognition is experimental. If you are absolutely sure about the text language (for example, Ukrainian), it is recommended to specify the language directly.
{{% /alert %}}

Value | Alphabet
----- | --------
`Language.EXT_LATIN` | Auto-detect [all supported Latin characters](/ocr/python-net/supported-characters/#extended-latin) and diacritics
`Language.CYRILLIC` | Auto-detect [all supported Cyrillic characters](/ocr/python-net/supported-characters/#cyrillic)
`Language.CHINESE` | All Chinese languages. Mixed-language Chinese/English texts also supported.
`Language.DEVANAGARI`<br />`Language.INDIC` | Indic texts based on Devanagari script, including mixed Devanagari/English texts.
`Language.EUROPEAN` | Mixed-language Cyrillic/English texts (_experimental_).
`Language.AFR` | Afrikaans
`Language.ALN` | Albanian
`Language.ARA` | Arabic, including texts in mixed Arabic/English
`Language.AWA` | Awadhi
`Language.AZB` | Azerbaijani (Azeri)
`Language.BCL` | Bikol
`Language.BEL` | Belarusan (Belorussian)
`Language.BEM` | Bemba (Chibemba)
`Language.BEW` | Betawi
`Language.BGC` | Haryanvi
`Language.BHO` | Bhojpuri
`Language.BHR` | Malagasy
`Language.BJJ` | Kanauji
`Language.BOS` | Bosnian
`Language.BUL` | Bulgarian
`Language.CAT` | Catalan
`Language.CCX` | Zhuang
`Language.CDO` | Min Dong
`Language.CEB` | Cebuano
`Language.CES` | Czech
`Language.CHE` | Chechen
`Language.CMN` | Mandarin (Chinese)
`Language.CPX` | Pu-Xian
`Language.DAN` | Danish
`Language.DEU` | German
`Language.DHD` | Dhundari
`Language.DIQ` | Dimli
`Language.DOC` | Dong
`Language.ENG` | English
`Language.EST` | Estonian
`Language.FIN` | Finnish
`Language.FRA` | French
`Language.GAN` | Gan
`Language.GAX` | Oromo
`Language.GBM` | Garhwali
`Language.GLG` | Galician
`Language.GLK` | Gilaki
`Language.GUZ` | Gusii
`Language.HAK` | Hakka
`Language.HAU` | Hausa
`Language.HBS` | Serbo-Croatian (Latin)
`Language.HIL` | Hiligaynon
`Language.HIN` | Hindi
`Language.HMN` | Hmong
`Language.HNE` | Chattisgarhi (Laria, Khaltahi)
`Language.HRV` | Croatian
`Language.HSN` | Xiang
`Language.HUN` | Hungarian (Magyar)
`Language.ILO` | Ilocano
`Language.IND` | Indonesian
`Language.ITA` | Italian
`Language.JPN` | Japanese (mixed texts in Japanese and English are also supported)
`Language.KAN` | Mixed-language Kannada/English texts.
`Language.KAZ` | Kazakh
`Language.KBD` | Kabardian
`Language.KFY` | Kumauni
`Language.KIN` | Rwanda
`Language.KLN` | Nandi
`Language.KMR` | Kurdish (Kurmanji)
`Language.KNC` | Kanuri
`Language.KNN` | Konkani
`Language.KON` | Kikongo
`Language.KOR` | Korean (mixed texts in Korean and English are also supported)
`Language.LATIN` | Latin
`Language.LAV` | Latvian
`Language.LIT` | Lithuanian
`Language.LMN` | Lamani (Lambadi)
`Language.LNC` | Occitan
`Language.LUO` | Luo
`Language.MAG` | Magahi
`Language.MAI` | Maithili
`Language.MAK` | Makassar (Makasar)
`Language.MAR` | Marathi
`Language.MER` | Meru
`Language.MIN` | Minangkabau
`Language.MLY` | Malay (Melayu)
`Language.MNP` | Min Bei
`Language.MTQ` | Muong
`Language.MTR` | Mewari
`Language.MUI` | Musi
`Language.MUP` | Malvi
`Language.NAN` | Min Nan
`Language.NBL` | Ndebele
`Language.NDS` | Low German
`Language.NEP` | Nepali
`Language.NLD` | Dutch
`Language.NOR` | Norwegian
`Language.NSO` | Sotho (Northern)
`Language.NYA` | Chichewa (Chewa, Nyanja)
`Language.PAG` | Pangasinan
`Language.PAM` | Kapampangan
`Language.PCC` | Bouyei (Buyi, Giáy)
`Language.PES` | Persian (Farsi), including texts in mixed Persian/English
`Language.PLM` | Palembang
`Language.POL` | Polish
`Language.POR` | Portuguese
`Language.QUC` | K'iche'
`Language.QXA` | Quechua
`Language.RJB` | Rajbanshi
`Language.RON` | Romanian
`Language.RUF` | Luguru
`Language.RUS` | Russian
`Language.RWR` | Marwari
`Language.SAS` | Sasak
`Language.SLK` | Slovak
`Language.SLV` | Slovene (Slovenian)
`Language.SNA` | Shona (Karanga)
`Language.SOM` | Somali
`Language.SOT` | Sotho (Southern)
`Language.SPA` | Spanish
`Language.SRP` | Serbian (Cyrillic)
`Language.SRR` | Serer-Sine
`Language.SSW` | Swati (Swazi)
`Language.SUK` | Sukuma
`Language.SUN` | Sundanese (Sunda)
`Language.SWE` | Swedish
`Language.SWH` | Swahili
`Language.TAM` | Mixed-language Tamil/English texts.
`Language.TEL` | Mixed-language Telugu/English texts.
`Language.TGL` | Tagalog (Pilipino)
`Language.TOI` | Tonga
`Language.TSN` | Tswana
`Language.TSO` | Tsonga
`Language.TUK` | Turkmen
`Language.TUM` | Tumbuka
`Language.TUR` | Turkish
`Language.UIG` | Uyghur, including texts in mixed Uyghur/English
`Language.UKR` | Ukrainian
`Language.UMB` | Umbundu
`Language.URD` | Urdu, including texts in mixed Urdu/English
`Language.VIE` | Vietnamese
`Language.VMW` | Makua (Makhuwa)
`Language.WAL` | Wolaytta
`Language.WAR` | Waray-Waray
`Language.WBR` | Wagdi
`Language.WTM` | Mewati
`Language.WUU` | Wu (Changzhou)
`Language.XHO` | Xhosa
`Language.YAO` | Yao
`Language.YOR` | Yoruba
`Language.YUE` | Cantonese
`Language.ZUL` | Zulu

If this parameter is omitted, the OCR engine will assume that the text is written in [extended Latin](/ocr/python-net/recognition-languages/#supported-characters).

{{% alert color="primary" %}}
Make sure you specify the correct language for the image. If you try to recognize Cyrillic text using `Language.ENG`, only the characters that look the same in both languages (for example, `с` and `c`) will be correctly recognized. Other characters will be replaced with similar-looking alternatives.
{{% /alert %}}

## Example

The following code sample demonstrates how to specify the recognition language:

```python
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
