---
title: Table.Table
second_title: Aspose.Words für .NET-API-Referenz
description: Table constructeur. Initialisiert eine neue Instanz von Tisch Klasse.
type: docs
weight: 10
url: /de/net/aspose.words.tables/table/table/
---
## Table constructor

Initialisiert eine neue Instanz von **Tisch** Klasse.

```csharp
public Table(DocumentBase doc)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| doc | DocumentBase | Das Besitzerdokument. |

### Bemerkungen

Wann **Tisch** erstellt wird, gehört es zum angegebenen Dokument, ist aber noch nicht Teil des Dokuments und **Elternknoten** ist Null.

Anhängen **Tisch** zum Dokument verwenden Sie InsertAfter oder InsertBefore in der Story, in der Sie die Tabelle einfügen möchten.

### Beispiele

Zeigt, wie eine Tabelle erstellt wird.

```csharp
Document doc = new Document();
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);

// Tabellen enthalten Zeilen, die Zellen enthalten, die Absätze haben können
// mit typischen Elementen wie Läufen, Formen und sogar anderen Tabellen.
// Das Aufrufen der "EnsureMinimum"-Methode für eine Tabelle stellt dies sicher
// Die Tabelle hat mindestens eine Zeile, eine Zelle und einen Absatz.
Row firstRow = new Row(doc);
table.AppendChild(firstRow);

Cell firstCell = new Cell(doc);
firstRow.AppendChild(firstCell);

Paragraph paragraph = new Paragraph(doc);
firstCell.AppendChild(paragraph);

// Text zum ersten Aufruf in der ersten Zeile der Tabelle hinzufügen.
Run run = new Run(doc, "Hello world!");
paragraph.AppendChild(run);

doc.Save(ArtifactsDir + "Table.CreateTable.docx");
```

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
* class [Table](../)
* namensraum [Aspose.Words.Tables](../../table/)
* Montage [Aspose.Words](../../../)


