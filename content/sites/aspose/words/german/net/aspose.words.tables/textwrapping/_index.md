---
title: Enum TextWrapping
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Tables.TextWrapping opsomming. Gibt an wie Text um die Tabelle gewickelt wird.
type: docs
weight: 6080
url: /de/net/aspose.words.tables/textwrapping/
---
## TextWrapping enumeration

Gibt an, wie Text um die Tabelle gewickelt wird.

```csharp
public enum TextWrapping
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| None | `0` | Text und Tabelle werden in der Reihenfolge ihres Erscheinens im Dokument angezeigt. |
| Around | `1` | Text wird um die Tabelle gewickelt und belegt den verfügbaren seitlichen Platz. |
| Default | `0` | Standardwert. |

### Beispiele

Zeigt, wie Sie mit Tabellentextumbruch arbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Cell 1");
builder.InsertCell();
builder.Write("Cell 2");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

builder.Font.Size = 16;
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

// Setzen Sie die "TextWrapping"-Eigenschaft auf "TextWrapping.Around", damit die Tabelle Text um sie herumfließt,
// und schieben Sie es in den folgenden Absatz, indem Sie die Position festlegen.
table.TextWrapping = TextWrapping.Around;
table.AbsoluteHorizontalDistance = 100;
table.AbsoluteVerticalDistance = 20;

doc.Save(ArtifactsDir + "Table.WrapText.docx");
```

### Siehe auch

* namensraum [Aspose.Words.Tables](../../aspose.words.tables/)
* Montage [Aspose.Words](../../)


