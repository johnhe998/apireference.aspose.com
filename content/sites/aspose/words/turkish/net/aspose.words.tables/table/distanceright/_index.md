---
title: Table.DistanceRight
second_title: Aspose.Words for .NET API Referansı
description: Table mülk. Sağdaki tablo ile çevresindeki metin arasındaki mesafeyi nokta cinsinden alır.
type: docs
weight: 140
url: /tr/net/aspose.words.tables/table/distanceright/
---
## Table.DistanceRight property

Sağdaki tablo ile çevresindeki metin arasındaki mesafeyi nokta cinsinden alır.

```csharp
public double DistanceRight { get; }
```

### Örnekler

Tablo sınırları ve metin arasındaki minimum mesafe işlemlerini gösterir.

```csharp
Document doc = new Document(MyDir + "Table wrapped by text.docx");

Table table = doc.FirstSection.Body.Tables[0];

Assert.AreEqual(25.9d, table.DistanceTop);
Assert.AreEqual(25.9d, table.DistanceBottom);
Assert.AreEqual(17.3d, table.DistanceLeft);
Assert.AreEqual(17.3d, table.DistanceRight);
```

### Ayrıca bakınız

* class [Table](../)
* ad alanı [Aspose.Words.Tables](../../table/)
* toplantı [Aspose.Words](../../../)


