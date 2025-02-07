---
title: CellFormat.Borders
second_title: Aspose.Words for .NET API Referansı
description: CellFormat mülk. Hücrenin kenarlıklarının koleksiyonunu alır.
type: docs
weight: 10
url: /tr/net/aspose.words.tables/cellformat/borders/
---
## CellFormat.Borders property

Hücrenin kenarlıklarının koleksiyonunu alır.

```csharp
public BorderCollection Borders { get; }
```

### Örnekler

İki tablodaki satırların tek bir tabloda nasıl birleştirileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

// Aşağıda bir belgeden tablo almanın iki yolu vardır.
// 1 - Bir Gövde düğümünün "Tablolar" koleksiyonundan:
Table firstTable = doc.FirstSection.Body.Tables[0];

// 2 - "GetChild" yöntemini kullanarak:
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);

// Geçerli tablodaki tüm satırları bir sonrakine ekleyin.
while (secondTable.HasChildNodes)
    firstTable.Rows.Add(secondTable.FirstRow);

// Boş tablo kapsayıcısını kaldırın.
secondTable.Remove();

doc.Save(ArtifactsDir + "Table.CombineTables.docx");
```

### Ayrıca bakınız

* class [BorderCollection](../../../aspose.words/bordercollection/)
* class [CellFormat](../)
* ad alanı [Aspose.Words.Tables](../../cellformat/)
* toplantı [Aspose.Words](../../../)


