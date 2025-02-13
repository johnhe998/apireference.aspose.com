---
title: Enum ConditionalStyleType
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.ConditionalStyleType opsomming. Stellt mögliche Tabellenbereiche dar für die bedingte Formatierung in einem Tabellenstil definiert werden kann.
type: docs
weight: 320
url: /de/net/aspose.words/conditionalstyletype/
---
## ConditionalStyleType enumeration

Stellt mögliche Tabellenbereiche dar, für die bedingte Formatierung in einem Tabellenstil definiert werden kann.

```csharp
public enum ConditionalStyleType
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| FirstRow | `0` | Gibt die Formatierung der ersten Zeile einer Tabelle an. |
| FirstColumn | `1` | Gibt die Formatierung der ersten Spalte einer Tabelle an. |
| LastRow | `2` | Gibt die Formatierung der letzten Zeile einer Tabelle an. |
| LastColumn | `3` | Gibt die Formatierung der letzten Spalte einer Tabelle an. |
| OddRowBanding | `4` | Gibt die Formatierung des Zeilenstreifens mit ungerader Nummer an. |
| OddColumnBanding | `5` | Gibt die Formatierung von ungeradzahligen Spaltenstreifen an. |
| EvenRowBanding | `6` | Gibt die Formatierung des Streifens mit geraden Zeilen an. |
| EvenColumnBanding | `7` | Gibt die Formatierung des geradzahligen Spaltenstreifens an. |
| TopLeftCell | `8` | Gibt die Formatierung der oberen linken Zelle einer Tabelle an. |
| TopRightCell | `9` | Gibt die Formatierung der oberen rechten Zelle einer Tabelle an. |
| BottomLeftCell | `10` | Gibt die Formatierung der unteren linken Zelle einer Tabelle an. |
| BottomRightCell | `11` | Gibt die Formatierung der unteren rechten Zelle einer Tabelle an. |

### Beispiele

Zeigt, wie mit bestimmten Bereichsstilen einer Tabelle gearbeitet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Cell 1");
builder.InsertCell();
builder.Write("Cell 2");
builder.EndRow();
builder.InsertCell();
builder.Write("Cell 3");
builder.InsertCell();
builder.Write("Cell 4");
builder.EndTable();

// Einen benutzerdefinierten Tabellenstil erstellen.
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");

// Bedingte Stile sind Formatierungsänderungen, die nur einige Zellen der Tabelle betreffen
// basierend auf einem Prädikat, z. B. die Zellen in der letzten Zeile.
// Im Folgenden finden Sie drei Möglichkeiten, auf die bedingten Stile eines Tabellenstils aus der Sammlung "ConditionalStyles" zuzugreifen.
// 1 - Nach Stiltyp:
tableStyle.ConditionalStyles[ConditionalStyleType.FirstRow].Shading.BackgroundPatternColor = Color.AliceBlue;

// 2 - Nach Index:
tableStyle.ConditionalStyles[0].Borders.Color = Color.Black;
tableStyle.ConditionalStyles[0].Borders.LineStyle = LineStyle.DotDash;
Assert.AreEqual(ConditionalStyleType.FirstRow, tableStyle.ConditionalStyles[0].Type);

// 3 - Als Eigenschaft:
tableStyle.ConditionalStyles.FirstRow.ParagraphFormat.Alignment = ParagraphAlignment.Center;

// Auffüllung und Textformatierung auf bedingte Stile anwenden.
tableStyle.ConditionalStyles.LastRow.BottomPadding = 10;
tableStyle.ConditionalStyles.LastRow.LeftPadding = 10;
tableStyle.ConditionalStyles.LastRow.RightPadding = 10;
tableStyle.ConditionalStyles.LastRow.TopPadding = 10;
tableStyle.ConditionalStyles.LastColumn.Font.Bold = true;

// Alle möglichen Stilbedingungen auflisten.
using (IEnumerator<ConditionalStyle> enumerator = tableStyle.ConditionalStyles.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        ConditionalStyle currentStyle = enumerator.Current;
        if (currentStyle != null) Console.WriteLine(currentStyle.Type);
    }
}

// Anwenden des benutzerdefinierten Stils, der alle bedingten Stile enthält, auf die Tabelle.
table.Style = tableStyle;

// Unser Stil wendet standardmäßig einige bedingte Stile an.
Assert.AreEqual(TableStyleOptions.FirstRow | TableStyleOptions.FirstColumn | TableStyleOptions.RowBands, 
    table.StyleOptions);

// Wir müssen alle anderen Stile selbst über die Eigenschaft "StyleOptions" aktivieren.
table.StyleOptions = table.StyleOptions | TableStyleOptions.LastRow | TableStyleOptions.LastColumn;

doc.Save(ArtifactsDir + "Table.ConditionalStyles.docx");
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


