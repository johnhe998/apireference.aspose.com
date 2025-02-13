---
title: InlineStory.IsInsertRevision
second_title: Aspose.Words för .NET API Referens
description: InlineStory fast egendom. Returnerar sant om det här objektet infogades i Microsoft Word medan ändringsspårning var aktiverad.
type: docs
weight: 40
url: /sv/net/aspose.words/inlinestory/isinsertrevision/
---
## InlineStory.IsInsertRevision property

Returnerar sant om det här objektet infogades i Microsoft Word medan ändringsspårning var aktiverad.

```csharp
public bool IsInsertRevision { get; }
```

### Exempel

Visar hur man visar revisionsrelaterade egenskaper för InlineStory-noder.

```csharp
Document doc = new Document(MyDir + "Revision footnotes.docx");

// När vi redigerar dokumentet medan alternativet "Spåra ändringar", som finns i via Granska -> Spårning,
// är aktiverat i Microsoft Word, de ändringar vi tillämpar räknas som revisioner.
// När vi redigerar ett dokument med Aspose.Words kan vi börja spåra revisioner med
// anropar dokumentets "StartTrackRevisions"-metod och stoppar spårningen genom att använda "StopTrackRevisions"-metoden.
// Vi kan antingen acceptera revisioner för att assimilera dem i dokumentet
// eller avvisa dem för att ångra och ignorera den föreslagna ändringen.
Assert.IsTrue(doc.HasRevisions);

List<Footnote> footnotes = doc.GetChildNodes(NodeType.Footnote, true).Cast<Footnote>().ToList();

Assert.AreEqual(5, footnotes.Count);

// Nedan finns fem typer av revisioner som kan flagga en InlineStory-nod.
// 1 - En "infoga" revision:
// Denna revidering sker när vi infogar text medan vi spårar ändringar.
Assert.IsTrue(footnotes[2].IsInsertRevision);

// 2 - En "flytta från" revision:
// När vi markerar text i Microsoft Word och sedan drar den till en annan plats i dokumentet
// medan du spårar ändringar visas två versioner.
// Revisionen "flytta från" är en kopia av texten som ursprungligen var innan vi flyttade den.
Assert.IsTrue(footnotes[4].IsMoveFromRevision);

// 3 - En "flytta till" revision:
// "Flytta till"-revisionen är texten som vi flyttade i sin nya position i dokumentet.
// "Flytta från" och "flytta till" revisioner visas i par för varje flytt revision vi utför.
// Att acceptera en flyttversion raderar "flytta från"-revisionen och dess text,
// och behåller texten från "flytta till"-revisionen.
// Att avvisa en flyttversion behåller omvänt "flytta från"-revisionen och tar bort "flytta till"-revisionen.
Assert.IsTrue(footnotes[1].IsMoveToRevision);

// 4 - En "radera" revision:
// Denna revidering sker när vi tar bort text medan vi spårar ändringar. När vi tar bort text som denna,
// det kommer att stanna i dokumentet som en revision tills vi antingen accepterar revisionen,
// som kommer att ta bort texten för gott, eller förkasta revisionen, vilket kommer att behålla texten vi raderade där den var.
Assert.IsTrue(footnotes[3].IsDeleteRevision);
```

### Se även

* class [InlineStory](../)
* namnutrymme [Aspose.Words](../../inlinestory/)
* hopsättning [Aspose.Words](../../../)


