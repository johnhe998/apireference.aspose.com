---
title: Table.RelativeVerticalAlignment
second_title: Aspose.Words for .NET API Referansı
description: Table mülk. Kayan tablo göreli dikey hizalamayı alır veya ayarlar.
type: docs
weight: 240
url: /tr/net/aspose.words.tables/table/relativeverticalalignment/
---
## Table.RelativeVerticalAlignment property

Kayan tablo göreli dikey hizalamayı alır veya ayarlar.

```csharp
public VerticalAlignment RelativeVerticalAlignment { get; set; }
```

### Örnekler

Kayan tabloların konumunun nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Table 1, cell 1");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

// Tablonun konumunu, bu durumda sağ alt köşe gibi sayfada bir yere ayarlayın.
table.RelativeVerticalAlignment = VerticalAlignment.Bottom;
table.RelativeHorizontalAlignment = HorizontalAlignment.Right;

table = builder.StartTable();
builder.InsertCell();
builder.Write("Table 2, cell 1");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

// Paragrafın tabloyu eklediğimiz konumundan noktalara yatay ve dikey bir öteleme de ayarlayabiliriz. 
table.AbsoluteVerticalDistance = 50;
table.AbsoluteHorizontalDistance = 100;

doc.Save(ArtifactsDir + "Table.ChangeFloatingTableProperties.docx");
```

### Ayrıca bakınız

* enum [VerticalAlignment](../../../aspose.words.drawing/verticalalignment/)
* class [Table](../)
* ad alanı [Aspose.Words.Tables](../../table/)
* toplantı [Aspose.Words](../../../)


