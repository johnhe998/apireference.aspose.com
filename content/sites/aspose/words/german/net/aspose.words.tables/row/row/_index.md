---
title: Row.Row
second_title: Aspose.Words für .NET-API-Referenz
description: Row constructeur. Initialisiert eine neue Instanz von Die Zeile Klasse.
type: docs
weight: 10
url: /de/net/aspose.words.tables/row/row/
---
## Row constructor

Initialisiert eine neue Instanz von **Die Zeile** Klasse.

```csharp
public Row(DocumentBase doc)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| doc | DocumentBase | Das Besitzerdokument. |

### Bemerkungen

Wann **Die Zeile** erstellt wird, gehört es zum angegebenen Dokument, ist aber noch nicht Teil des Dokuments und **Elternknoten** ist Null.

Anhängen **Die Zeile**zum Dokument verwenden Sie InsertAfter oder InsertBefore für die Tabelle, in der Sie die Zeile einfügen möchten.

### Beispiele

Zeigt, wie Sie eine verschachtelte Tabelle erstellen, ohne einen Document Builder zu verwenden.

```csharp
public void CreateNestedTable()
{
    Document doc = new Document();

    // Erstellen Sie die äußere Tabelle mit drei Zeilen und vier Spalten und fügen Sie sie dann dem Dokument hinzu.
    Table outerTable = CreateTable(doc, 3, 4, "Outer Table");
    doc.FirstSection.Body.AppendChild(outerTable);

    // Erstellen Sie eine weitere Tabelle mit zwei Zeilen und zwei Spalten und fügen Sie sie dann in die erste Zelle der ersten Tabelle ein.
    Table innerTable = CreateTable(doc, 2, 2, "Inner Table");
    outerTable.FirstRow.FirstCell.AppendChild(innerTable);

    doc.Save(ArtifactsDir + "Table.CreateNestedTable.docx");
}

/// <summary>
/// Erstellt eine neue Tabelle im Dokument mit den angegebenen Abmessungen und Text in jeder Zelle.
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

    // Sie können die Eigenschaften "Titel" und "Beschreibung" verwenden, um Ihrer Tabelle jeweils einen Titel und eine Beschreibung hinzuzufügen.
    // Die Tabelle muss mindestens eine Zeile haben, bevor wir diese Eigenschaften verwenden können.
    // Diese Eigenschaften sind sinnvoll für ISO/IEC 29500-konforme .docx-Dokumente (siehe Klasse OoxmlCompliance).
    // Wenn wir das Dokument in Pre-ISO/IEC 29500-Formaten speichern, ignoriert Microsoft Word diese Eigenschaften.
    table.Title = "Aspose table title";
    table.Description = "Aspose table description";

    return table;
}
```

### Siehe auch

* class [DocumentBase](../../../aspose.words/documentbase/)
* class [Row](../)
* namensraum [Aspose.Words.Tables](../../row/)
* Montage [Aspose.Words](../../../)


