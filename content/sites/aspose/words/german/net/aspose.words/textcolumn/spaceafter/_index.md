---
title: TextColumn.SpaceAfter
second_title: Aspose.Words für .NET-API-Referenz
description: TextColumn eigendom. Holt oder setzt den Abstand zwischen dieser Spalte und der nächsten Spalte in Punkt. Für die letzte Spalte nicht erforderlich.
type: docs
weight: 10
url: /de/net/aspose.words/textcolumn/spaceafter/
---
## TextColumn.SpaceAfter property

Holt oder setzt den Abstand zwischen dieser Spalte und der nächsten Spalte in Punkt. Für die letzte Spalte nicht erforderlich.

```csharp
public double SpaceAfter { get; set; }
```

### Beispiele

Zeigt, wie Spalten mit ungleichmäßigen Abständen erstellt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
PageSetup pageSetup = builder.PageSetup;

TextColumnCollection columns = pageSetup.TextColumns;
columns.EvenlySpaced = false;
columns.SetCount(2);

// Bestimmen Sie den verfügbaren Platz zum Anordnen von Spalten.
double contentWidth = pageSetup.PageWidth - pageSetup.LeftMargin - pageSetup.RightMargin;

Assert.AreEqual(470.30d, contentWidth, 0.01d);

// Setze die erste Spalte auf schmal.
TextColumn column = columns[0];
column.Width = 100;
column.SpaceAfter = 20;

// Legen Sie die zweite Spalte so fest, dass sie den Rest des verfügbaren Platzes innerhalb der Seitenränder einnimmt.
column = columns[1];
column.Width = contentWidth - column.Width - column.SpaceAfter;

builder.Writeln("Narrow column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Wide column 2.");

doc.Save(ArtifactsDir + "PageSetup.CustomColumnWidth.docx");
```

### Siehe auch

* class [TextColumn](../)
* namensraum [Aspose.Words](../../textcolumn/)
* Montage [Aspose.Words](../../../)


