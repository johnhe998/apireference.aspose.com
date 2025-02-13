---
title: CompositeNode.HasChildNodes
second_title: Aspose.Words for .NET API Referansı
description: CompositeNode mülk. Bu düğümün herhangi bir alt düğümü varsa doğru döndürür.
type: docs
weight: 40
url: /tr/net/aspose.words/compositenode/haschildnodes/
---
## CompositeNode.HasChildNodes property

Bu düğümün herhangi bir alt düğümü varsa doğru döndürür.

```csharp
public bool HasChildNodes { get; }
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

* class [CompositeNode](../)
* ad alanı [Aspose.Words](../../compositenode/)
* toplantı [Aspose.Words](../../../)


