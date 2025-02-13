---
title: Table.EnsureMinimum
second_title: Aspose.Words for .NET API Referansı
description: Table yöntem. Tabloda satır yoksa bir satır oluşturur ve ekler Sıra .
type: docs
weight: 400
url: /tr/net/aspose.words.tables/table/ensureminimum/
---
## Table.EnsureMinimum method

Tabloda satır yoksa, bir satır oluşturur ve ekler **Sıra** .

```csharp
public void EnsureMinimum()
```

### Örnekler

Bir tablo düğümünün, içerik eklemek için ihtiyaç duyduğumuz düğümleri içerdiğinden nasıl emin olunacağını gösterir.

```csharp
Document doc = new Document();
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);

// Tablolar, paragraflar içerebilen hücreler içeren satırlar içerir
// koşular, şekiller ve hatta diğer tablolar gibi tipik öğelerle.
// Yeni tablomuzda bu düğümlerin hiçbiri yok ve o gelene kadar ona içerik ekleyemeyiz.
Assert.AreEqual(0, table.GetChildNodes(NodeType.Any, true).Count);

// Bir tabloda "EnsureMinimum" yöntemini çağırmak,
// tabloda en az bir satır ve boş bir paragraf içeren bir hücre var.
table.EnsureMinimum();
table.FirstRow.FirstCell.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));
```

### Ayrıca bakınız

* class [Table](../)
* ad alanı [Aspose.Words.Tables](../../table/)
* toplantı [Aspose.Words](../../../)


