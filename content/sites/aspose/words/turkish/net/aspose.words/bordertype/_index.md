---
title: Enum BorderType
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.BorderType Sıralama. Bir sınırın kenarlarını belirtir.
type: docs
weight: 90
url: /tr/net/aspose.words/bordertype/
---
## BorderType enumeration

Bir sınırın kenarlarını belirtir.

```csharp
public enum BorderType
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| None | `-1` | Varsayılan değer. |
| Bottom | `0` | Bir paragrafın veya tablo hücresinin alt kenarlığını belirtir. |
| Left | `1` | Bir paragrafın veya tablo hücresinin sol kenarlığını belirtir. |
| Right | `2` | Bir paragrafın veya tablo hücresinin sağ kenarlığını belirtir. |
| Top | `3` | Bir paragrafın veya tablo hücresinin üst kenarlığını belirtir. |
| Horizontal | `4` | Tablodaki hücreler veya uyumlu paragraflar arasındaki yatay sınırı belirtir. |
| Vertical | `5` | Tablodaki hücreler arasındaki dikey sınırı belirtir. |
| DiagonalDown | `6` | Bir tablo hücresindeki çapraz kenarlığı belirtir. |
| DiagonalUp | `7` | Bir tablo hücresindeki çapraz kenarlığı belirtir. |

### Örnekler

Üst kenarlıklı bir paragrafın nasıl ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Border topBorder = builder.ParagraphFormat.Borders[BorderType.Top];
topBorder.Color = Color.Red;
topBorder.LineWidth = 4.0d;
topBorder.LineStyle = LineStyle.DashSmallGap;

builder.Writeln("Text with a red top border.");

doc.Save(ArtifactsDir + "Border.ParagraphTopBorder.docx");
```

### Ayrıca bakınız

* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


