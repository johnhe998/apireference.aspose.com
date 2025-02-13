---
title: Enum TableStyleOptions
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Tables.TableStyleOptions opsomming. Gibt an wie der Tabellenstil auf eine Tabelle angewendet wird.
type: docs
weight: 6070
url: /de/net/aspose.words.tables/tablestyleoptions/
---
## TableStyleOptions enumeration

Gibt an, wie der Tabellenstil auf eine Tabelle angewendet wird.

```csharp
[Flags]
public enum TableStyleOptions
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| None | `0` | Es wird keine Tabellenformatierung angewendet. |
| FirstRow | `20` | Bedingte Formatierung der ersten Zeile anwenden. |
| LastRow | `40` | Bedingte Formatierung der letzten Zeile anwenden. |
| FirstColumn | `80` | Bedingte Formatierung für 1 erste Spalte anwenden. |
| LastColumn | `100` | Bedingte Formatierung der letzten Spalte anwenden. |
| RowBands | `200` | Bedingte Zeilenbandformatierung anwenden. |
| ColumnBands | `400` | Bedingte Formatierung für Spaltenbanding anwenden. |
| Default2003 | `600` | Zeilen- und Spaltenbanding wird angewendet. Dies ist die Standardeinstellung von Microsoft Word für alte Formate wie DOC, WML und RTF. |
| Default | `2A0` | Dies sind die Standardeinstellungen von Microsoft Word. |

### Beispiele

Zeigt, wie eine neue Tabelle erstellt wird, während ein Stil angewendet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();

// Wir müssen mindestens eine Zeile einfügen, bevor wir eine Tabellenformatierung festlegen.
builder.InsertCell();

// Legen Sie den verwendeten Tabellenstil basierend auf der Stilkennung fest.
// Beachten Sie, dass beim Speichern im .doc-Format nicht alle Tabellenstile verfügbar sind.
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;

// Wenden Sie den Stil teilweise auf Features der Tabelle an, basierend auf Prädikaten, und erstellen Sie dann die Tabelle.
table.StyleOptions =
    TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
table.AutoFit(AutoFitBehavior.AutoFitToContents);

builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder.InsertCell();
builder.Writeln("Quantity (kg)");
builder.EndRow();

builder.InsertCell();
builder.Writeln("Apples");
builder.InsertCell();
builder.Writeln("20");
builder.EndRow();

builder.InsertCell();
builder.Writeln("Bananas");
builder.InsertCell();
builder.Writeln("40");
builder.EndRow();

builder.InsertCell();
builder.Writeln("Carrots");
builder.InsertCell();
builder.Writeln("50");
builder.EndRow();

doc.Save(ArtifactsDir + "DocumentBuilder.InsertTableWithStyle.docx");
```

### Siehe auch

* property [StyleOptions](../table/styleoptions/)
* namensraum [Aspose.Words.Tables](../../aspose.words.tables/)
* Montage [Aspose.Words](../../)


