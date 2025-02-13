---
title: Class TabStop
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.TabStop klass. Representerar ett enda anpassat tabbstopp. De TabStop objektet är en medlem av the TabStopCollection samling.
type: docs
weight: 5900
url: /sv/net/aspose.words/tabstop/
---
## TabStop class

Representerar ett enda anpassat tabbstopp. De **TabStop** objektet är en medlem av the [`TabStopCollection`](../tabstopcollection/) samling.

```csharp
public sealed class TabStop
```

## Konstruktörer

| namn | Beskrivning |
| --- | --- |
| [TabStop](tabstop/#constructor)(double) | Initierar en ny instans av den här klassen. |
| [TabStop](tabstop/#constructor_1)(double, TabAlignment, TabLeader) | Initierar en ny instans av den här klassen. |

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [Alignment](../../aspose.words/tabstop/alignment/) { get; set; } | Hämtar eller ställer in justeringen av text vid detta tabbstopp. |
| [IsClear](../../aspose.words/tabstop/isclear/) { get; } | Returnerar sant om detta tabbstopp rensar alla befintliga tabbstopp i denna position. |
| [Leader](../../aspose.words/tabstop/leader/) { get; set; } | Hämtar eller ställer in typen av ledarraden som visas under tabbtecknet. |
| [Position](../../aspose.words/tabstop/position/) { get; } | Får tabbstoppets position i poäng. |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [Equals](../../aspose.words/tabstop/equals/#equals)(TabStop) | Jämför med den angivna TabStop. |
| override [GetHashCode](../../aspose.words/tabstop/gethashcode/)() | Beräknar hashkod för detta objekt. |

### Anmärkningar

Normalt anger ett tabbstopp en position där ett tabbstopp finns. Men eftersom tabbstopp kan ärvas från överordnade stilar, kan det behövas för det underordnade objektet att uttryckligen definiera att det inte finns något tabbstopp vid en given position. För att rensa ett ärvt tabbstopp vid en given position, skapa en **TabStop** objekt och set [`Alignment`](./alignment/) till`TabAlignment.Clear`.

För mer information se[`TabStopCollection`](../tabstopcollection/).

### Exempel

Visar hur man ändrar positionen för höger tabbstopp i innehållsförteckningsrelaterade stycken.

```csharp
Document doc = new Document(MyDir + "Table of contents.docx");

// Iterera genom alla stycken med TOC resultatbaserade stilar; detta är vilken stil som helst mellan TOC och TOC9.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true).OfType<Paragraph>())
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        // Få den första fliken som används i det här stycket, detta bör vara den flik som används för att anpassa sidnumren.
        TabStop tab = para.ParagraphFormat.TabStops[0];

        // Ersätt den första standardfliken, sluta med ett anpassat tabbstopp.
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }

doc.Save(ArtifactsDir + "Styles.ChangeTocsTabStops.docx");
```

### Se även

* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


