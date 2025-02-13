---
title: Class TextColumn
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.TextColumn klas. Repräsentiert eine einzelne Textspalte. TextSpalte ist Mitglied derTextColumnCollection Sammlung. Die Textspalten Sammlung enthält alle Spalten in einem Abschnitt eines Dokuments.
type: docs
weight: 6090
url: /de/net/aspose.words/textcolumn/
---
## TextColumn class

Repräsentiert eine einzelne Textspalte. **TextSpalte** ist Mitglied der[`TextColumnCollection`](../textcolumncollection/) Sammlung. Die **Textspalten** Sammlung enthält alle Spalten in einem Abschnitt eines Dokuments.

```csharp
public class TextColumn
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [SpaceAfter](../../aspose.words/textcolumn/spaceafter/) { get; set; } | Holt oder setzt den Abstand zwischen dieser Spalte und der nächsten Spalte in Punkt. Für die letzte Spalte nicht erforderlich. |
| [Width](../../aspose.words/textcolumn/width/) { get; set; } | Liest oder setzt die Breite der Textspalte in Punkt. |

### Bemerkungen

**TextSpalte** Objekte werden nur verwendet, um Spalten mit benutzerdefinierter Breite und Abstand anzugeben. Wenn Sie wollen dass die Spalten im Dokument gleich breit sind, setzen Sie TextColumns.[`EvenlySpaced`](../textcolumncollection/evenlyspaced/) zu **Stimmt**.

Wenn ein neues **TextSpalte** erstellt wird, werden Breite und Abstand auf Null gesetzt.

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

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


