---
title: Class TextColumnCollection
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.TextColumnCollection klass. En samling avTextColumn objekt som representerar alla textkolumner i en del av ett dokument.
type: docs
weight: 6100
url: /sv/net/aspose.words/textcolumncollection/
---
## TextColumnCollection class

En samling av[`TextColumn`](../textcolumn/) objekt som representerar alla textkolumner i en del av ett dokument.

```csharp
public class TextColumnCollection
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [Count](../../aspose.words/textcolumncollection/count/) { get; } | Hämtar antalet kolumner i avsnittet av ett dokument. |
| [EvenlySpaced](../../aspose.words/textcolumncollection/evenlyspaced/) { get; set; } | **Sann** om textkolumner är lika breda och jämnt fördelade. |
| [Item](../../aspose.words/textcolumncollection/item/) { get; } | Returnerar en textkolumn vid det angivna indexet. |
| [LineBetween](../../aspose.words/textcolumncollection/linebetween/) { get; set; } | När **Sann** , lägger till en vertikal linje mellan kolumner. |
| [Spacing](../../aspose.words/textcolumncollection/spacing/) { get; set; } | När kolumner är jämnt fördelade, hämtas eller ställer in mängden utrymme mellan varje kolumn i poäng. |
| [Width](../../aspose.words/textcolumncollection/width/) { get; } | När kolumner är jämnt fördelade, får bredden på kolumnerna. |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [SetCount](../../aspose.words/textcolumncollection/setcount/)(int) | Ordnar text i det angivna antalet textkolumner. |

### Anmärkningar

Använda sig av[`SetCount`](./setcount/) för att ställa in antalet textkolumner.

Ställ in för att göra alla kolumner lika breda och jämnt fördelade[`EvenlySpaced`](./evenlyspaced/) till **Sann** och ange mängden utrymme mellan kolumnerna i[`Spacing`](./spacing/). MS Word kommer att automatiskt beräkna kolumnbredder.

Om du har **Jämnt mellanrum** satt till **falsk**måste du ange bredd och avstånd för varje kolumn individuellt. Använd indexeraren för att komma åt individen[`TextColumn`](../textcolumn/) objekt.

När du använder anpassade kolumnbredder, se till att summan av alla kolumnbredder och avstånd mellan dem är lika med sidbredd minus vänster och höger sidmarginaler.

### Exempel

Visar hur man skapar flera jämnt fördelade kolumner i ett avsnitt.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TextColumnCollection columns = builder.PageSetup.TextColumns;
columns.Spacing = 100;
columns.SetCount(2);

builder.Writeln("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Column 2.");

doc.Save(ArtifactsDir + "PageSetup.ColumnsSameWidth.docx");
```

### Se även

* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


