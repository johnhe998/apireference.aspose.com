---
title: Class BorderCollection
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.BorderCollection klass. En samling gränsobjekt.
type: docs
weight: 80
url: /sv/net/aspose.words/bordercollection/
---
## BorderCollection class

En samling gränsobjekt.

```csharp
public sealed class BorderCollection : IEnumerable<Border>
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [Bottom](../../aspose.words/bordercollection/bottom/) { get; } | Får den nedre kanten. |
| [Color](../../aspose.words/bordercollection/color/) { get; set; } | Hämtar eller ställer in kantfärgen. |
| [Count](../../aspose.words/bordercollection/count/) { get; } | Hämtar antalet ramar i samlingen. |
| [DistanceFromText](../../aspose.words/bordercollection/distancefromtext/) { get; set; } | Hämtar eller ställer in avståndet mellan gränsen från text i punkter. |
| [Horizontal](../../aspose.words/bordercollection/horizontal/) { get; } | Hämtar den horisontella ram som används mellan celler eller överensstämmande stycken. |
| [Item](../../aspose.words/bordercollection/item/) { get; } | Hämtar ett kantobjekt efter kanttyp. (2 indexers) |
| [Left](../../aspose.words/bordercollection/left/) { get; } | Får den vänstra kanten. |
| [LineStyle](../../aspose.words/bordercollection/linestyle/) { get; set; } | Hämtar eller ställer in kantstilen. |
| [LineWidth](../../aspose.words/bordercollection/linewidth/) { get; set; } | Hämtar eller ställer in kantbredden i punkter. |
| [Right](../../aspose.words/bordercollection/right/) { get; } | Får rätt kant. |
| [Shadow](../../aspose.words/bordercollection/shadow/) { get; set; } | Hämtar eller ställer in ett värde som anger om gränsen har en skugga. |
| [Top](../../aspose.words/bordercollection/top/) { get; } | Får den övre kanten. |
| [Vertical](../../aspose.words/bordercollection/vertical/) { get; } | Hämtar den vertikala gränsen som används mellan celler. |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [ClearFormatting](../../aspose.words/bordercollection/clearformatting/)() | Tar bort alla kanter för ett objekt. |
| [Equals](../../aspose.words/bordercollection/equals/#equals)(BorderCollection) | Jämför samlingar av ramar. |
| [GetEnumerator](../../aspose.words/bordercollection/getenumerator/)() | Returnerar ett uppräkningsobjekt som kan användas för att iterera över alla gränser i samlingen. |

### Anmärkningar

Olika dokumentelement har olika ramar. Till exempel har ParagraphFormat Bottom, Left, Right och Top-kanter. Du kan ange olika formatering för varje kant oberoende av varandra eller räkna upp genom alla kanter och tillämpa samma formatering.

### Exempel

Visar hur man infogar ett stycke med en övre kant.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Border topBorder = builder.ParagraphFormat.Borders[BorderType.Top];
topBorder.Color = Color.Red;
topBorder.LineWidth = 4.0d;
topBorder.LineStyle = LineStyle.DashSmallGap;

builder.Writeln("Text with a red top border.");

doc.Save(ArtifactsDir + "Border.ParagraphTopBorder.docx");
```

### Se även

* class [Border](../border/)
* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


