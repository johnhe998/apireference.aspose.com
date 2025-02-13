---
title: Cell.EnsureMinimum
second_title: Aspose.Words for .NET API Referansı
description: Cell yöntem. Son alt öğe bir paragraf değilse boş bir paragraf oluşturur ve ekler.
type: docs
weight: 120
url: /tr/net/aspose.words.tables/cell/ensureminimum/
---
## Cell.EnsureMinimum method

Son alt öğe bir paragraf değilse, boş bir paragraf oluşturur ve ekler.

```csharp
public void EnsureMinimum()
```

### Örnekler

Bir hücre düğümünün, ona içerik eklemeye başlamak için ihtiyaç duyduğumuz düğümleri içerdiğinden nasıl emin olunacağını gösterir.

```csharp
Document doc = new Document();
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
Row row = new Row(doc);
table.AppendChild(row);
Cell cell = new Cell(doc);
row.AppendChild(cell);

// Hücreler, koşular, şekiller ve hatta diğer tablolar gibi tipik öğeler içeren paragraflar içerebilir.
// Yeni hücremizde herhangi bir paragraf yok ve o gelene kadar ona run ve shape düğümleri gibi içerikler ekleyemiyoruz.
Assert.AreEqual(0, cell.GetChildNodes(NodeType.Any, true).Count);

// Bir hücrede "EnsureMinimum" yöntemini çağırmak,
// hücrede daha sonra içerik ekleyebileceğimiz en az bir boş paragraf var.
cell.EnsureMinimum();
cell.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));
```

### Ayrıca bakınız

* class [Cell](../)
* ad alanı [Aspose.Words.Tables](../../cell/)
* toplantı [Aspose.Words](../../../)


