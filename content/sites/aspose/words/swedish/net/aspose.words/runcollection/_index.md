---
title: Class RunCollection
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.RunCollection klass. Ger maskinskriven åtkomst till en samling avRun noder.
type: docs
weight: 4570
url: /sv/net/aspose.words/runcollection/
---
## RunCollection class

Ger maskinskriven åtkomst till en samling av[`Run`](../run/) noder.

```csharp
public class RunCollection : NodeCollection
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | Hämtar antalet noder i samlingen. |
| [Item](../../aspose.words/runcollection/item/) { get; } | Hämtar en **Springa** vid det givna indexet. (2 indexers) |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [Add](../../aspose.words/nodecollection/add/)(Node) | Lägger till en nod i slutet av samlingen. |
| [Clear](../../aspose.words/nodecollection/clear/)() | Tar bort alla noder från den här samlingen och från dokumentet. |
| [Contains](../../aspose.words/nodecollection/contains/)(Node) | Bestämmer om en nod finns i samlingen. |
| [GetEnumerator](../../aspose.words/nodecollection/getenumerator/)() | Ger en enkel "foreach" stil iteration över samlingen av noder. |
| [IndexOf](../../aspose.words/nodecollection/indexof/)(Node) | Returnerar det nollbaserade indexet för den angivna noden. |
| [Insert](../../aspose.words/nodecollection/insert/)(int, Node) | Infogar en nod i samlingen vid det angivna indexet. |
| [Remove](../../aspose.words/nodecollection/remove/)(Node) | Tar bort noden från samlingen och från dokumentet. |
| [RemoveAt](../../aspose.words/nodecollection/removeat/)(int) | Tar bort noden vid det angivna indexet från samlingen och från dokumentet. |
| [ToArray](../../aspose.words/runcollection/toarray/#toarray_1)() | Kopierar alla körningar från samlingen till en ny array av körningar. (2 methods) |

### Exempel

Visar hur man bestämmer revisionstypen för en inline-nod.

```csharp
Document doc = new Document(MyDir + "Revision runs.docx");

// När vi redigerar dokumentet medan alternativet "Spåra ändringar", som finns i via Granska -> Spårning,
// är aktiverat i Microsoft Word, de ändringar vi tillämpar räknas som revisioner.
// När vi redigerar ett dokument med Aspose.Words kan vi börja spåra revisioner med
// anropar dokumentets "StartTrackRevisions"-metod och stoppar spårningen genom att använda "StopTrackRevisions"-metoden.
// Vi kan antingen acceptera revisioner för att assimilera dem i dokumentet
// eller avvisa dem för att effektivt ändra den föreslagna ändringen.
Assert.AreEqual(6, doc.Revisions.Count);

// Föräldernoden för en revision är den körning som revisionen avser. En Run är en Inline-nod.
Run run = (Run)doc.Revisions[0].ParentNode;

Paragraph firstParagraph = run.ParentParagraph;
RunCollection runs = firstParagraph.Runs;

Assert.AreEqual(6, runs.ToArray().Length);

// Nedan finns fem typer av revisioner som kan flagga en Inline-nod.
// 1 - En "infoga" revision:
// Denna revidering sker när vi infogar text medan vi spårar ändringar.
Assert.IsTrue(runs[2].IsInsertRevision);

// 2 - En "format"-revision:
// Denna revidering sker när vi ändrar formateringen av text medan vi spårar ändringar.
Assert.IsTrue(runs[2].IsFormatRevision);

// 3 - En "flytta från" revision:
// När vi markerar text i Microsoft Word och sedan drar den till en annan plats i dokumentet
// medan du spårar ändringar visas två versioner.
// Revisionen "flytta från" är en kopia av texten som ursprungligen var innan vi flyttade den.
Assert.IsTrue(runs[4].IsMoveFromRevision);

// 4 - En "flytta till" revision:
// "Flytta till"-revisionen är texten som vi flyttade i sin nya position i dokumentet.
// "Flytta från" och "flytta till" revisioner visas i par för varje flytt revision vi utför.
// Att acceptera en flyttversion raderar "flytta från"-revisionen och dess text,
// och behåller texten från "flytta till"-revisionen.
// Att avvisa en flyttversion behåller omvänt "flytta från"-revisionen och tar bort "flytta till"-revisionen.
Assert.IsTrue(runs[1].IsMoveToRevision);

// 5 - En "radera" revision:
// Denna revidering sker när vi tar bort text medan vi spårar ändringar. När vi tar bort text som denna,
// det kommer att stanna i dokumentet som en revision tills vi antingen accepterar revisionen,
// som kommer att ta bort texten för gott, eller förkasta revisionen, vilket kommer att behålla texten vi raderade där den var.
Assert.IsTrue(runs[5].IsDeleteRevision);
```

### Se även

* class [NodeCollection](../nodecollection/)
* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


