---
title: Table.Title
second_title: Aspose.Words for .NET API Referansı
description: Table mülk. Bu tablonun başlığını alır veya ayarlar. Tabloda yer alan bilgilerin alternatif bir metin gösterimini sağlar.
type: docs
weight: 320
url: /tr/net/aspose.words.tables/table/title/
---
## Table.Title property

Bu tablonun başlığını alır veya ayarlar. Tabloda yer alan bilgilerin alternatif bir metin gösterimini sağlar.

```csharp
public string Title { get; set; }
```

### Notlar

Varsayılan değer boş bir dizedir.

Bu özellik, ISO/IEC 29500 uyumlu DOCX belgeleri için anlamlıdır ([`OoxmlCompliance`](../../../aspose.words.saving/ooxmlcompliance/)). ISO/IEC 29500 öncesi biçimlere kaydedildiğinde, özellik yok sayılır.

### Örnekler

Belge oluşturucu kullanmadan iç içe tablonun nasıl oluşturulacağını gösterir.

```csharp
public void CreateNestedTable()
{
    Document doc = new Document();

    // Üç satır ve dört sütunlu dış tabloyu oluşturun ve ardından belgeye ekleyin.
    Table outerTable = CreateTable(doc, 3, 4, "Outer Table");
    doc.FirstSection.Body.AppendChild(outerTable);

    // İki satır ve iki sütun içeren başka bir tablo oluşturun ve ardından bunu ilk tablonun ilk hücresine ekleyin.
    Table innerTable = CreateTable(doc, 2, 2, "Inner Table");
    outerTable.FirstRow.FirstCell.AppendChild(innerTable);

    doc.Save(ArtifactsDir + "Table.CreateNestedTable.docx");
}

/// <summary>
/// Her hücrede verilen boyutlar ve metin ile belgede yeni bir tablo oluşturur.
/// </summary>
private static Table CreateTable(Document doc, int rowCount, int cellCount, string cellText)
{
    Table table = new Table(doc);

    for (int rowId = 1; rowId <= rowCount; rowId++)
    {
        Row row = new Row(doc);
        table.AppendChild(row);

        for (int cellId = 1; cellId <= cellCount; cellId++)
        {
            Cell cell = new Cell(doc);
            cell.AppendChild(new Paragraph(doc));
            cell.FirstParagraph.AppendChild(new Run(doc, cellText));

            row.AppendChild(cell);
        }
    }

    // Tablonuza sırasıyla başlık ve açıklama eklemek için "Title" ve "Description" özelliklerini kullanabilirsiniz.
    // Bu özellikleri kullanabilmemiz için tablonun en az bir satırı olmalıdır.
    // Bu özellikler, ISO/IEC 29500 uyumlu .docx belgeleri için anlamlıdır (bkz. OoxmlCompliance sınıfı).
    // Belgeyi ISO/IEC 29500 öncesi formatlarda kaydedersek, Microsoft Word bu özellikleri yok sayar.
    table.Title = "Aspose table title";
    table.Description = "Aspose table description";

    return table;
}
```

### Ayrıca bakınız

* class [Table](../)
* ad alanı [Aspose.Words.Tables](../../table/)
* toplantı [Aspose.Words](../../../)


