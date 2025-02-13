---
title: Table.AllowCellSpacing
second_title: Aspose.Words for .NET API Referansı
description: Table mülk. Hücreler arasında boşluk bırakmaya izin ver seçeneğini alır veya ayarlar.
type: docs
weight: 60
url: /tr/net/aspose.words.tables/table/allowcellspacing/
---
## Table.AllowCellSpacing property

"Hücreler arasında boşluk bırakmaya izin ver" seçeneğini alır veya ayarlar.

```csharp
public bool AllowCellSpacing { get; set; }
```

### Örnekler

Tablodaki tek tek hücreler arasında boşluk bırakmanın nasıl etkinleştirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Animal");
builder.InsertCell();
builder.Write("Class");
builder.EndRow();
builder.InsertCell();
builder.Write("Dog");
builder.InsertCell();
builder.Write("Mammal");
builder.EndTable();

table.CellSpacing = 3;

// Hücreler arasında boşluk bırakmak için "AllowCellSpacing" özelliğini "true" olarak ayarlayın
// nokta olarak "CellSpacing" özelliğinin değerine eşit büyüklükte.
// Hücre aralığını devre dışı bırakmak için "AllowCellSpacing" özelliğini "false" olarak ayarlayın
// ve "CellSpacing" özelliğinin değerini yok sayın.
table.AllowCellSpacing = allowCellSpacing;

doc.Save(ArtifactsDir + "Table.AllowCellSpacing.html");

// "CellSpacing" özelliğinin ayarlanması hücre aralığını otomatik olarak etkinleştirecektir.
table.CellSpacing = 5;

Assert.True(table.AllowCellSpacing);
```

### Ayrıca bakınız

* class [Table](../)
* ad alanı [Aspose.Words.Tables](../../table/)
* toplantı [Aspose.Words](../../../)


