---
title: PreferredWidth.Value
second_title: Aspose.Words for .NET API Referansı
description: PreferredWidth mülk. Tercih edilen genişlik değerini alır. Ölçü birimi şurada belirtilmiştirType özellik.
type: docs
weight: 50
url: /tr/net/aspose.words.tables/preferredwidth/value/
---
## PreferredWidth.Value property

Tercih edilen genişlik değerini alır. Ölçü birimi şurada belirtilmiştir:[`Type`](../type/) özellik.

```csharp
public double Value { get; }
```

### Örnekler

Bir tablo hücresinin tercih edilen genişlik tipinin ve değerinin nasıl doğrulanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

Table table = doc.FirstSection.Body.Tables[0];
Cell firstCell = table.FirstRow.FirstCell;

Assert.AreEqual(PreferredWidthType.Percent, firstCell.CellFormat.PreferredWidth.Type);
Assert.AreEqual(11.16d, firstCell.CellFormat.PreferredWidth.Value);
```

### Ayrıca bakınız

* class [PreferredWidth](../)
* ad alanı [Aspose.Words.Tables](../../preferredwidth/)
* toplantı [Aspose.Words](../../../)


