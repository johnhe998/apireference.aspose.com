---
title: Story.Tables
second_title: Aspose.Words for .NET API Referansı
description: Story mülk. Öykünün doğrudan alt öğeleri olan tabloların bir koleksiyonunu alır.
type: docs
weight: 50
url: /tr/net/aspose.words/story/tables/
---
## Story.Tables property

Öykünün doğrudan alt öğeleri olan tabloların bir koleksiyonunu alır.

```csharp
public TableCollection Tables { get; }
```

### Örnekler

Bir belgedeki tüm tabloların ilk ve son satırlarının nasıl kaldırılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

TableCollection tables = doc.FirstSection.Body.Tables;

Assert.AreEqual(5, tables[0].Rows.Count);
Assert.AreEqual(4, tables[1].Rows.Count);

foreach (Table table in tables.OfType<Table>())
{
    table.FirstRow?.Remove();
    table.LastRow?.Remove();
}

Assert.AreEqual(3, tables[0].Rows.Count);
Assert.AreEqual(2, tables[1].Rows.Count);
```

### Ayrıca bakınız

* class [TableCollection](../../../aspose.words.tables/tablecollection/)
* class [Story](../)
* ad alanı [Aspose.Words](../../story/)
* toplantı [Aspose.Words](../../../)


