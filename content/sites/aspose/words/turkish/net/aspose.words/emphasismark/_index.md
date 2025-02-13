---
title: Enum EmphasisMark
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.EmphasisMark Sıralama. Olası vurgu işareti türlerini belirtir.
type: docs
weight: 1310
url: /tr/net/aspose.words/emphasismark/
---
## EmphasisMark enumeration

Olası vurgu işareti türlerini belirtir.

```csharp
public enum EmphasisMark
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| None | `0` | Vurgu işareti yok. |
| OverSolidCircle | `1` | Vurgu işareti, metnin üzerinde görüntülenen düz siyah bir dairedir. |
| OverComma | `2` | Vurgu işareti, metnin üzerinde görüntülenen bir virgül karakteridir. |
| OverWhiteCircle | `3` | Vurgu işareti, metnin üzerinde görüntülenen boş beyaz bir dairedir. |
| UnderSolidCircle | `4` | Vurgu işareti, metnin altında görüntülenen düz siyah bir dairedir. |

### Örnekler

Glif karakterinin üstünde/altında işlenen ek karakterin nasıl ekleneceğini gösterir.

```csharp
DocumentBuilder builder = new DocumentBuilder();

// Olası vurgu işareti türleri:
// https://apireference.aspose.com/words/net/aspose.words/emphasismark
builder.Font.EmphasisMark = emphasisMark; 

builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");

builder.Document.Save(ArtifactsDir + "Fonts.SetEmphasisMark.docx");
```

### Ayrıca bakınız

* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


