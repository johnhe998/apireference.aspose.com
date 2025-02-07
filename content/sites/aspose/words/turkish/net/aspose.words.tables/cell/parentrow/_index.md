---
title: Cell.ParentRow
second_title: Aspose.Words for .NET API Referansı
description: Cell mülk. Hücrenin üst satırını döndürür.
type: docs
weight: 90
url: /tr/net/aspose.words.tables/cell/parentrow/
---
## Cell.ParentRow property

Hücrenin üst satırını döndürür.

```csharp
public Row ParentRow { get; }
```

### Notlar

Eşittir`(Satır)FirstNonMarkupÜst Düğüm`.

### Örnekler

Aynı sayfada bir arada kalacak bir tablonun nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Table spanning two pages.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Tablodaki her paragraf için KeepWithNext'i etkinleştirme
// son satırdaki son olanlar, tablonun birden çok sayfaya bölünmesini engeller.
foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true).OfType<Cell>())
    foreach (Paragraph para in cell.Paragraphs.OfType<Paragraph>())
    {
        Assert.True(para.IsInCell);

        if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
            para.ParagraphFormat.KeepWithNext = true;
    }

doc.Save(ArtifactsDir + "Table.KeepTableTogether.docx");
```

### Ayrıca bakınız

* class [Row](../../row/)
* class [Cell](../)
* ad alanı [Aspose.Words.Tables](../../cell/)
* toplantı [Aspose.Words](../../../)


