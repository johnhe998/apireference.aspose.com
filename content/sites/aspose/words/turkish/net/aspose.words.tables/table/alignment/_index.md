---
title: Table.Alignment
second_title: Aspose.Words for .NET API Referansı
description: Table mülk. Bir satır içi tablonun belgede nasıl hizalanacağını belirtir.
type: docs
weight: 40
url: /tr/net/aspose.words.tables/table/alignment/
---
## Table.Alignment property

Bir satır içi tablonun belgede nasıl hizalanacağını belirtir.

```csharp
public TableAlignment Alignment { get; set; }
```

### Notlar

Varsayılan değerLeft.

### Örnekler

Bir tabloya anahat kenarlığının nasıl uygulanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Tabloyu sayfanın ortasına hizalayın.
table.Alignment = TableAlignment.Center;

// Tablodaki mevcut kenarlıkları ve gölgelemeleri temizleyin.
table.ClearBorders();
table.ClearShading();

// Tablonun ana hatlarına yeşil kenarlıklar ekleyin.
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);

// Hücreleri açık yeşil düz renkle doldurun.
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);

doc.Save(ArtifactsDir + "Table.SetOutlineBorders.docx");
```

### Ayrıca bakınız

* enum [TableAlignment](../../tablealignment/)
* class [Table](../)
* ad alanı [Aspose.Words.Tables](../../table/)
* toplantı [Aspose.Words](../../../)


