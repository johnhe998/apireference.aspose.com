---
title: Class ParagraphCollection
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.ParagraphCollection klass. Ger maskinskriven åtkomst till en samling avParagraph noder.
type: docs
weight: 4170
url: /sv/net/aspose.words/paragraphcollection/
---
## ParagraphCollection class

Ger maskinskriven åtkomst till en samling av[`Paragraph`](../paragraph/) noder.

```csharp
public class ParagraphCollection : NodeCollection
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | Hämtar antalet noder i samlingen. |
| [Item](../../aspose.words/paragraphcollection/item/) { get; } | Hämtar en **Paragraf** vid det givna indexet. (2 indexers) |

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
| [ToArray](../../aspose.words/paragraphcollection/toarray/#toarray_1)() | Kopierar alla stycken från samlingen till en ny uppsättning stycken. (2 methods) |

### Exempel

Visar hur man kontrollerar om ett stycke är en flyttversion.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

// Det här dokumentet innehåller "Move"-versioner, som visas när vi markerar text med markören,
// och sedan dra den för att flytta den till en annan plats
// medan du spårar revisioner i Microsoft Word via "Review" -> "Spåra ändringar".
Assert.AreEqual(6, doc.Revisions.Count(r => r.RevisionType == RevisionType.Moving));

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

// Flytta revisioner består av par av "Flytta från" och "Flytta till" versioner. 
// Dessa ändringar är potentiella ändringar av dokumentet som vi antingen kan acceptera eller förkasta.
// Innan vi accepterar/avvisar en flyttrevision, dokumentet
// måste hålla reda på både avgångs- och ankomstdestinationerna för texten.
// Andra och fjärde stycket definierar en sådan revidering, och båda har alltså samma innehåll.
Assert.AreEqual(paragraphs[1].GetText(), paragraphs[3].GetText());

// Revisionen "Flytta från" är stycket där vi drog texten från.
// Om vi accepterar revideringen kommer denna paragraf att försvinna,
// och den andra kommer att finnas kvar och inte längre vara en revision.
Assert.True(paragraphs[1].IsMoveFromRevision);

// Revisionen "Flytta till" är stycket dit vi drog texten till.
// Om vi förkastar revisionen försvinner istället denna paragraf, och den andra kommer att finnas kvar.
Assert.True(paragraphs[3].IsMoveToRevision);
```

### Se även

* class [NodeCollection](../nodecollection/)
* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


