---
title: Enum ListTrailingCharacter
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Lists.ListTrailingCharacter uppräkning. Anger tecknet som skiljer listetiketten från texten i stycket.
type: docs
weight: 3340
url: /sv/net/aspose.words.lists/listtrailingcharacter/
---
## ListTrailingCharacter enumeration

Anger tecknet som skiljer listetiketten från texten i stycket.

```csharp
public enum ListTrailingCharacter
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Tab | `0` | Ett tabbtecken placeras mellan listetiketten och texten i stycket. |
| Space | `1` | Ett blanksteg placeras mellan listetiketten och texten i stycket. |
| Nothing | `2` | Det finns inget skiljetecken mellan listetiketten och texten i stycket. |

### Anmärkningar

Används som ett värde för[`TrailingCharacter`](../listlevel/trailingcharacter/) fast egendom.

### Exempel

Visar hur du använder anpassad listformatering på stycken när du använder DocumentBuilder.

```csharp
Document doc = new Document();

// En lista låter oss organisera och dekorera uppsättningar av stycken med prefixsymboler och indrag.
// Vi kan skapa kapslade listor genom att öka indragsnivån. 
// Vi kan börja och avsluta en lista genom att använda en dokumentbyggares "ListFormat"-egenskap. 
// Varje stycke som vi lägger till mellan en listas början och slutet kommer att bli ett objekt i listan.
// Skapa en lista från en Microsoft Word-mall och anpassa de två första av listnivåerna.
List list = doc.Lists.Add(ListTemplate.NumberDefault);

ListLevel listLevel = list.ListLevels[0];
listLevel.Font.Color = Color.Red;
listLevel.Font.Size = 24;
listLevel.NumberStyle = NumberStyle.OrdinalText;
listLevel.StartAt = 21;
listLevel.NumberFormat = "\x0000";

listLevel.NumberPosition = -36;
listLevel.TextPosition = 144;
listLevel.TabPosition = 144;

listLevel = list.ListLevels[1];
listLevel.Alignment = ListLevelAlignment.Right;
listLevel.NumberStyle = NumberStyle.Bullet;
listLevel.Font.Name = "Wingdings";
listLevel.Font.Color = Color.Blue;
listLevel.Font.Size = 24;

// Detta NumberFormat-värde skapar stjärnformade punktlistsymboler.
listLevel.NumberFormat = "\xf0af";
listLevel.TrailingCharacter = ListTrailingCharacter.Space;
listLevel.NumberPosition = 144;

// Skapa stycken och tillämpa båda listnivåerna i vår anpassade listformatering på dem.
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.List = list;
builder.Writeln("The quick brown fox...");
builder.Writeln("The quick brown fox...");

builder.ListFormat.ListIndent();
builder.Writeln("jumped over the lazy dog.");
builder.Writeln("jumped over the lazy dog.");

builder.ListFormat.ListOutdent();
builder.Writeln("The quick brown fox...");

builder.ListFormat.RemoveNumbers();

builder.Document.Save(ArtifactsDir + "Lists.CreateCustomList.docx");
```

### Se även

* namnutrymme [Aspose.Words.Lists](../../aspose.words.lists/)
* hopsättning [Aspose.Words](../../)


