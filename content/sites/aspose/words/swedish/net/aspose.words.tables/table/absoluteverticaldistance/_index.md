---
title: Table.AbsoluteVerticalDistance
second_title: Aspose.Words för .NET API Referens
description: Table fast egendom. Hämtar eller ställer in den absoluta vertikala flytande tabellens position specificerad av tabellens egenskaper i poäng. Standardvärdet är 0.
type: docs
weight: 30
url: /sv/net/aspose.words.tables/table/absoluteverticaldistance/
---
## Table.AbsoluteVerticalDistance property

Hämtar eller ställer in den absoluta vertikala flytande tabellens position specificerad av tabellens egenskaper, i poäng. Standardvärdet är 0.

```csharp
public double AbsoluteVerticalDistance { get; set; }
```

### Exempel

Visar hur man ställer in placeringen av flytande bord.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Table 1, cell 1");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

// Ställ in tabellens plats till en plats på sidan, som i det här fallet det nedre högra hörnet.
table.RelativeVerticalAlignment = VerticalAlignment.Bottom;
table.RelativeHorizontalAlignment = HorizontalAlignment.Right;

table = builder.StartTable();
builder.InsertCell();
builder.Write("Table 2, cell 1");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

// Vi kan också ställa in en horisontell och vertikal förskjutning i punkter från styckets plats där vi infogade tabellen. 
table.AbsoluteVerticalDistance = 50;
table.AbsoluteHorizontalDistance = 100;

doc.Save(ArtifactsDir + "Table.ChangeFloatingTableProperties.docx");
```

### Se även

* class [Table](../)
* namnutrymme [Aspose.Words.Tables](../../table/)
* hopsättning [Aspose.Words](../../../)


