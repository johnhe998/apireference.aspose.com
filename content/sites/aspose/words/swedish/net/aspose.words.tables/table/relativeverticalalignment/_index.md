---
title: Table.RelativeVerticalAlignment
second_title: Aspose.Words för .NET API Referens
description: Table fast egendom. Hämtar eller ställer in flytande tabell relativ vertikal justering.
type: docs
weight: 240
url: /sv/net/aspose.words.tables/table/relativeverticalalignment/
---
## Table.RelativeVerticalAlignment property

Hämtar eller ställer in flytande tabell relativ vertikal justering.

```csharp
public VerticalAlignment RelativeVerticalAlignment { get; set; }
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

* enum [VerticalAlignment](../../../aspose.words.drawing/verticalalignment/)
* class [Table](../)
* namnutrymme [Aspose.Words.Tables](../../table/)
* hopsättning [Aspose.Words](../../../)


