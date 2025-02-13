---
title: Document.MailMerge
second_title: Aspose.Words for .NET API Referansı
description: Document mülk. Bir döndürür Posta birleştirme belge için adres mektup birleştirme işlevini temsil eden nesne.
type: docs
weight: 240
url: /tr/net/aspose.words/document/mailmerge/
---
## Document.MailMerge property

Bir döndürür **Posta birleştirme** belge için adres mektup birleştirme işlevini temsil eden nesne.

```csharp
public MailMerge MailMerge { get; }
```

### Örnekler

DataTable'daki verilerle adres mektup birleştirmenin nasıl yürütüleceğini gösterir.

```csharp
public void ExecuteDataTable()
{
    DataTable table = new DataTable("Test");
    table.Columns.Add("CustomerName");
    table.Columns.Add("Address");
    table.Rows.Add(new object[] { "Thomas Hardy", "120 Hanover Sq., London" });
    table.Rows.Add(new object[] { "Paolo Accorti", "Via Monte Bianco 34, Torino" });

    // Aşağıda, adres mektup birleştirme için veri kaynağı olarak bir DataTable kullanmanın iki yolu bulunmaktadır.
    // 1 - Tablodaki her satır için bir çıktı adres mektup birleştirme belgesi oluşturmak üzere adres mektup birleştirme için tüm tabloyu kullanın:
    Document doc = CreateSourceDocExecuteDataTable();

    doc.MailMerge.Execute(table);

    doc.Save(ArtifactsDir + "MailMerge.ExecuteDataTable.WholeTable.docx");

    // 2 - Bir çıktı adres mektup birleştirme belgesi oluşturmak için tablonun bir satırını kullanın:
    doc = CreateSourceDocExecuteDataTable();

    doc.MailMerge.Execute(table.Rows[1]);

    doc.Save(ArtifactsDir + "MailMerge.ExecuteDataTable.OneRow.docx");
}

/// <summary>
/// Adres mektup birleştirme kaynak belgesi oluşturur.
/// </summary>
private static Document CreateSourceDocExecuteDataTable()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(" MERGEFIELD CustomerName ");
    builder.InsertParagraph();
    builder.InsertField(" MERGEFIELD Address ");

    return doc;
}
```

### Ayrıca bakınız

* class [MailMerge](../../../aspose.words.mailmerging/mailmerge/)
* class [Document](../)
* ad alanı [Aspose.Words](../../document/)
* toplantı [Aspose.Words](../../../)


