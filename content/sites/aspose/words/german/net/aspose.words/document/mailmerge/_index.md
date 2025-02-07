---
title: Document.MailMerge
second_title: Aspose.Words für .NET-API-Referenz
description: Document eigendom. Gibt a zurück Seriendruck Objekt das die Seriendruckfunktion für das Dokument darstellt.
type: docs
weight: 240
url: /de/net/aspose.words/document/mailmerge/
---
## Document.MailMerge property

Gibt a zurück **Seriendruck** Objekt, das die Seriendruckfunktion für das Dokument darstellt.

```csharp
public MailMerge MailMerge { get; }
```

### Beispiele

Zeigt, wie ein Seriendruck mit Daten aus einer DataTable ausgeführt wird.

```csharp
public void ExecuteDataTable()
{
    DataTable table = new DataTable("Test");
    table.Columns.Add("CustomerName");
    table.Columns.Add("Address");
    table.Rows.Add(new object[] { "Thomas Hardy", "120 Hanover Sq., London" });
    table.Rows.Add(new object[] { "Paolo Accorti", "Via Monte Bianco 34, Torino" });

    // Im Folgenden finden Sie zwei Möglichkeiten, eine DataTable als Datenquelle für einen Seriendruck zu verwenden.
    // 1 - Verwenden Sie die gesamte Tabelle für den Seriendruck, um ein Ausgabe-Seriendruckdokument für jede Zeile in der Tabelle zu erstellen:
    Document doc = CreateSourceDocExecuteDataTable();

    doc.MailMerge.Execute(table);

    doc.Save(ArtifactsDir + "MailMerge.ExecuteDataTable.WholeTable.docx");

    // 2 - Verwenden Sie eine Zeile der Tabelle, um ein Seriendruckdokument zu erstellen:
    doc = CreateSourceDocExecuteDataTable();

    doc.MailMerge.Execute(table.Rows[1]);

    doc.Save(ArtifactsDir + "MailMerge.ExecuteDataTable.OneRow.docx");
}

/// <summary>
/// Erstellt ein Seriendruck-Quelldokument.
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

### Siehe auch

* class [MailMerge](../../../aspose.words.mailmerging/mailmerge/)
* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)


