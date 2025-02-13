---
title: Enum ParagraphAlignment
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.ParagraphAlignment uppräkning. Anger textjustering i ett stycke.
type: docs
weight: 4160
url: /sv/net/aspose.words/paragraphalignment/
---
## ParagraphAlignment enumeration

Anger textjustering i ett stycke.

```csharp
public enum ParagraphAlignment
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Left | `0` | Texten är vänsterjusterad. |
| Center | `1` | Text centreras horisontellt. |
| Right | `2` | Texten är högerjusterad. |
| Justify | `3` | Text är justerad till både vänster och höger. |
| Distributed | `4` | Texten är jämnt fördelad. |
| ArabicMediumKashida | `5` | Endast arabiska. Kashida-längden för text utökas till en medellängd som bestäms av konsumenten. |
| ArabicHighKashida | `7` | Endast arabiska. Kashida-längden för text utökas till bredast möjliga längd. |
| ArabicLowKashida | `8` | Endast arabiska. Kashida-längden för text utökas till en något längre längd. |
| ThaiDistributed | `9` | Endast thailändska. Texten är motiverad med en optimering för thailändska. |
| MathElementCenterAsGroup | `10` | Det enda Math-elementet på en rad, justerat som 'Centrerad som grupp'. |

### Exempel

Visar hur man konstruerar ett Aspose.Words-dokument för hand.

```csharp
Document doc = new Document();

// Ett tomt dokument innehåller ett avsnitt, en brödtext och ett stycke.
// Anropa metoden "RemoveAllChildren" för att ta bort alla dessa noder,
// och slutar med en dokumentnod utan underordnade.
doc.RemoveAllChildren();

// Det här dokumentet har nu inga sammansatta underordnade noder som vi kan lägga till innehåll till.
// Om vi vill redigera den måste vi fylla på dess nodsamling.
// Skapa först ett nytt avsnitt och lägg sedan till det som ett underordnat dokument i rotdokumentnoden.
Section section = new Section(doc);
doc.AppendChild(section);

// Ställ in några sidinställningar för avsnittet.
section.PageSetup.SectionStart = SectionStart.NewPage;
section.PageSetup.PaperSize = PaperSize.Letter;

// En sektion behöver en kropp som kommer att innehålla och visa allt dess innehåll
// på sidan mellan avsnittets sidhuvud och sidfot.
Body body = new Body(doc);
section.AppendChild(body);

// Skapa ett stycke, ange några formateringsegenskaper och lägg sedan till det som ett underordnat stycke i brödtexten.
Paragraph para = new Paragraph(doc);

para.ParagraphFormat.StyleName = "Heading 1";
para.ParagraphFormat.Alignment = ParagraphAlignment.Center;

body.AppendChild(para);

// Slutligen, lägg till lite innehåll för att göra dokumentet. Skapa en löprunda,
// ställ in dess utseende och innehåll och lägg sedan till det som ett barn till stycket.
Run run = new Run(doc);
run.Text = "Hello World!";
run.Font.Color = Color.Red;
para.AppendChild(run);

Assert.AreEqual("Hello World!", doc.GetText().Trim());

doc.Save(ArtifactsDir + "Section.CreateManually.docx");
```

### Se även

* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


