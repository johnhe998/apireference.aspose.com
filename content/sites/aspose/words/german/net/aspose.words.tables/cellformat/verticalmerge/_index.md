---
title: CellFormat.VerticalMerge
second_title: Aspose.Words für .NET-API-Referenz
description: CellFormat eigendom. Gibt an wie die Zelle vertikal mit anderen Zellen verbunden wird.
type: docs
weight: 120
url: /de/net/aspose.words.tables/cellformat/verticalmerge/
---
## CellFormat.VerticalMerge property

Gibt an, wie die Zelle vertikal mit anderen Zellen verbunden wird.

```csharp
public CellMerge VerticalMerge { get; set; }
```

### Bemerkungen

Zellen können nur dann vertikal verbunden werden, wenn ihre linken und rechten Grenzen identisch sind.

Wenn Zellen vertikal verbunden werden, werden die Anzeigebereiche der verbundenen Zellen konsolidiert. Der konsolidierte Bereich wird verwendet, um den Inhalt der ersten vertikal verbundenen Zelle anzuzeigen und alle anderen vertikal verbundenen Zellen müssen leer sein.

### Beispiele

Druckt den horizontalen und vertikalen Zusammenführungstyp einer Zelle.

```csharp
public void CheckCellsMerged()
{
    Document doc = new Document(MyDir + "Table with merged cells.docx");
    Table table = doc.FirstSection.Body.Tables[0];

    foreach (Row row in table.Rows.OfType<Row>())
        foreach (Cell cell in row.Cells.OfType<Cell>())
            Console.WriteLine(PrintCellMergeType(cell));
}

public string PrintCellMergeType(Cell cell)
{
    bool isHorizontallyMerged = cell.CellFormat.HorizontalMerge != CellMerge.None;
    bool isVerticallyMerged = cell.CellFormat.VerticalMerge != CellMerge.None;
    string cellLocation =
        $"R{cell.ParentRow.ParentTable.IndexOf(cell.ParentRow) + 1}, C{cell.ParentRow.IndexOf(cell) + 1}";

    if (isHorizontallyMerged && isVerticallyMerged)
        return $"The cell at {cellLocation} is both horizontally and vertically merged";
    if (isHorizontallyMerged)
        return $"The cell at {cellLocation} is horizontally merged.";

    return isVerticallyMerged ? $"The cell at {cellLocation} is vertically merged" : $"The cell at {cellLocation} is not merged";
}
```

Zeigt, wie Tabellenzellen vertikal verbunden werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Eine Zelle in die erste Spalte der ersten Zeile einfügen.
// Diese Zelle ist die erste in einer Reihe vertikal verbundener Zellen.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Füge eine Zelle in die zweite Spalte der ersten Zeile ein und beende dann die Zeile.
// Konfigurieren Sie außerdem den Builder, um das vertikale Zusammenführen in erstellten Zellen zu deaktivieren.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in unmerged cell.");
builder.EndRow();

// Eine Zelle in die erste Spalte der zweiten Zeile einfügen. 
// Anstatt Textinhalte hinzuzufügen, werden wir diese Zelle mit der ersten Zelle zusammenführen, die wir direkt darüber hinzugefügt haben.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Eine weitere unabhängige Zelle in die zweite Spalte der zweiten Zeile einfügen.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in unmerged cell.");
builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "CellFormat.VerticalMerge.docx");
```

### Siehe auch

* enum [CellMerge](../../cellmerge/)
* class [CellFormat](../)
* namensraum [Aspose.Words.Tables](../../cellformat/)
* Montage [Aspose.Words](../../../)


