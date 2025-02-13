---
title: FileFormatUtil.SaveFormatToLoadFormat
second_title: Aspose.Words för .NET API Referens
description: FileFormatUtil metod. Konverterar enSaveFormat värde till aLoadFormat värde om möjligt.
type: docs
weight: 90
url: /sv/net/aspose.words/fileformatutil/saveformattoloadformat/
---
## FileFormatUtil.SaveFormatToLoadFormat method

Konverterar en[`SaveFormat`](../../saveformat/) värde till a[`LoadFormat`](../../loadformat/) värde om möjligt.

```csharp
public static LoadFormat SaveFormatToLoadFormat(SaveFormat saveFormat)
```

### Undantag

| undantag | skick |
| --- | --- |
| ArgumentException | Kastar när det inte går att konvertera. |

### Exempel

Visar hur man konverterar ett sparat format till dess motsvarande laddningsformat.

```csharp
Assert.AreEqual(LoadFormat.Html, FileFormatUtil.SaveFormatToLoadFormat(SaveFormat.Html));

// Vissa filtyper kan ha dokument sparade till, men inte laddade från att använda Aspose.Words.
// Om vi försöker konvertera ett lagringsformat av en sådan typ till ett laddningsformat, kommer ett undantag att kastas.
Assert.Throws<ArgumentException>(() => FileFormatUtil.SaveFormatToLoadFormat(SaveFormat.Jpeg));
```

### Se även

* enum [LoadFormat](../../loadformat/)
* enum [SaveFormat](../../saveformat/)
* class [FileFormatUtil](../)
* namnutrymme [Aspose.Words](../../fileformatutil/)
* hopsättning [Aspose.Words](../../../)


