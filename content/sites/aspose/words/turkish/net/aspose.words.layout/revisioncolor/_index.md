---
title: Enum RevisionColor
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Layout.RevisionColor Sıralama. Belge revizyonlarının rengini belirlemeye izin verir.
type: docs
weight: 3180
url: /tr/net/aspose.words.layout/revisioncolor/
---
## RevisionColor enumeration

Belge revizyonlarının rengini belirlemeye izin verir.

```csharp
public enum RevisionColor
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Auto | `0` | Varsayılan. |
| Black | `1` | 000000 rengi temsil eder. |
| Blue | `2` | 2e97d3 rengi temsil eder. |
| BrightGreen | `3` | 84a35b rengi temsil eder. |
| ClassicBlue | `4` | 0000ff rengi temsil eder. |
| ClassicRed | `5` | ff0000 rengi temsil eder. |
| DarkBlue | `6` | 376e96 rengini temsil eder. |
| DarkRed | `7` | 881824 rengi temsil eder. |
| DarkYellow | `8` | e09a2b rengini temsil eder. |
| Gray25 | `9` | a0a3a9 rengini temsil eder. |
| Gray50 | `10` | 50565e rengi temsil eder. |
| Green | `11` | 2c6234 rengini temsil eder. |
| Pink | `12` | ce338f rengini temsil eder. |
| Red | `13` | b5082e rengini temsil eder. |
| Teal | `14` | 1b9cab rengini temsil eder. |
| Turquoise | `15` | 3eafc2 rengini temsil eder. |
| Violet | `16` | 633277 rengi temsil eder. |
| White | `17` | ffffff rengini temsil eder. |
| Yellow | `18` | Fad272 rengini temsil eder. |
| NoHighlight | `19` | Revizyon değişikliklerini vurgulamak için renk kullanılmaz. |
| ByAuthor | `20` | Her yazarın revizyonları, önceden tanımlanmış bir yüksek kontrastlı renk grubundan vurgulanmak üzere kendi rengini alır. |

### Örnekler

İşlenmiş bir çıktı belgesindeki revizyonların görünümünün nasıl değiştirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bir revizyon ekleyin, ardından tüm revizyonların rengini yeşil olarak değiştirin.
builder.Writeln("This is not a revision.");
doc.StartTrackRevisions("John Doe", DateTime.Now);
builder.Writeln("This is a revision.");
doc.StopTrackRevisions();
builder.Writeln("This is not a revision.");

// Revize edilen her satırın solunda görünen çubuğu kaldırın.
doc.LayoutOptions.RevisionOptions.InsertedTextColor = RevisionColor.BrightGreen;
doc.LayoutOptions.RevisionOptions.ShowRevisionBars = false;

doc.Save(ArtifactsDir + "Document.LayoutOptionsRevisions.pdf");
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Layout](../../aspose.words.layout/)
* toplantı [Aspose.Words](../../)


