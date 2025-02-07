---
title: Class TabStopCollection
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.TabStopCollection klass. En samling avTabStopobjekt som representerar anpassade flikar för ett stycke eller en stil.
type: docs
weight: 5910
url: /sv/net/aspose.words/tabstopcollection/
---
## TabStopCollection class

En samling av[`TabStop`](../tabstop/)objekt som representerar anpassade flikar för ett stycke eller en stil.

```csharp
public class TabStopCollection : InternableComplexAttr
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [Count](../../aspose.words/tabstopcollection/count/) { get; } | Hämtar antalet tabbstopp i samlingen. |
| [Item](../../aspose.words/tabstopcollection/item/) { get; } | Får ett tabbstopp vid det givna indexet. (2 indexers) |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [Add](../../aspose.words/tabstopcollection/add/#add)(TabStop) | Lägger till eller ersätter ett tabbstopp i samlingen. |
| [Add](../../aspose.words/tabstopcollection/add/#add_1)(double, TabAlignment, TabLeader) | Lägger till eller ersätter ett tabbstopp i samlingen. |
| [After](../../aspose.words/tabstopcollection/after/)(double) | Får ett första tabbstopp till höger om den angivna positionen. |
| [Before](../../aspose.words/tabstopcollection/before/)(double) | Får ett första tabbstopp till vänster om den angivna positionen. |
| [Clear](../../aspose.words/tabstopcollection/clear/)() | Tar bort alla tabbstopppositioner. |
| override [Equals](../../aspose.words/tabstopcollection/equals/#equals_1)(object) | Bestämmer om det angivna objektet har samma värde som det aktuella objektet. |
| [Equals](../../aspose.words/tabstopcollection/equals/#equals)(TabStopCollection) | Bestämmer om den angivna TabStopCollection är lika i värde med den aktuella TabStopCollection. |
| override [GetHashCode](../../aspose.words/tabstopcollection/gethashcode/)() | Fungerar som en hashfunktion för denna typ. |
| [GetIndexByPosition](../../aspose.words/tabstopcollection/getindexbyposition/)(double) | Hämtar indexet för ett tabbstopp med angiven position i poäng. |
| [GetPositionByIndex](../../aspose.words/tabstopcollection/getpositionbyindex/)(int) | Hämtar positionen (i poäng) för tabbstoppet vid det angivna indexet. |
| [RemoveByIndex](../../aspose.words/tabstopcollection/removebyindex/)(int) | Tar bort ett tabbstopp vid det angivna indexet från samlingen. |
| [RemoveByPosition](../../aspose.words/tabstopcollection/removebyposition/)(double) | Tar bort ett tabbstopp vid angiven position från samlingen. |

### Anmärkningar

I Microsoft Word-dokument kan ett tabbstopp definieras i egenskaperna för en stycke -stil eller direkt i egenskaperna för ett stycke. En stil kan baseras på en annan stil. Därför är den kompletta uppsättningen tabbstopp för ett givet objekt en kombination av tabbstopp definierade direkt på detta objekt och tabbstopp som ärvs från de överordnade stilarna.

I Aspose.Words, när du får en **TabStops** samling för ett stycke eller en stil, den innehåller endast de anpassade tabbstopp som definierats direkt för detta stycke eller format. Samlingen inkluderar inte tabbstopp definierade i de överordnade stilarna eller standardtabbstoppen.

### Exempel

Visar hur man arbetar med ett dokuments samling av tabbstopp.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TabStopCollection tabStops = builder.ParagraphFormat.TabStops;

// 72 poäng är en "tum" på tabbstoppslinjalen i Microsoft Word.
tabStops.Add(new TabStop(72.0));
tabStops.Add(new TabStop(432.0, TabAlignment.Right, TabLeader.Dashes));

Assert.AreEqual(2, tabStops.Count);
Assert.IsFalse(tabStops[0].IsClear);
Assert.IsFalse(tabStops[0].Equals(tabStops[1]));

// Varje "tab"-tecken tar byggarens markör till platsen för nästa tabbstopp.
builder.Writeln("Start\tTab 1\tTab 2");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

Assert.AreEqual(2, paragraphs.Count);

// Varje stycke får sin tabbstoppsamling, som klonar dess värden från dokumentbyggarens tabbstoppsamling.
Assert.AreEqual(paragraphs[0].ParagraphFormat.TabStops, paragraphs[1].ParagraphFormat.TabStops);
Assert.AreNotSame(paragraphs[0].ParagraphFormat.TabStops, paragraphs[1].ParagraphFormat.TabStops);

// En tabbstoppsamling kan peka oss till TabStops före och efter vissa positioner.
Assert.AreEqual(72.0, tabStops.Before(100.0).Position);
Assert.AreEqual(432.0, tabStops.After(100.0).Position);

// Vi kan rensa ett styckes tabbstoppsamling för att återgå till standardbeteendet för tabbning.
paragraphs[1].ParagraphFormat.TabStops.Clear();

Assert.AreEqual(0, paragraphs[1].ParagraphFormat.TabStops.Count);

doc.Save(ArtifactsDir + "TabStopCollection.TabStopCollection.docx");
```

### Se även

* class [InternableComplexAttr](../internablecomplexattr/)
* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


