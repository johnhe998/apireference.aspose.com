---
title: BorderCollection.Item
second_title: Aspose.Words för .NET API Referens
description: BorderCollection fast egendom. Hämtar ett kantobjekt efter kanttyp.
type: docs
weight: 60
url: /sv/net/aspose.words/bordercollection/item/
---
## BorderCollection indexer (1 of 2)

Hämtar ett kantobjekt efter kanttyp.

```csharp
public Border this[BorderType borderType] { get; }
```

| Parameter | Beskrivning |
| --- | --- |
| borderType | A[`BorderType`](../../bordertype/) värde som anger vilken typ av gräns som ska hämtas. |

### Anmärkningar

Observera att inte alla gränser finns för olika dokumentelement. Denna metod ger ett undantag om du begär en gräns som inte är tillämplig på det aktuella objektet.

### Exempel

Visar hur man dekorerar text med kanter och skuggningar.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

BorderCollection borders = builder.ParagraphFormat.Borders;
borders.DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;

Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = Color.LightCoral;
shading.ForegroundPatternColor = Color.LightSalmon;

builder.Write("This paragraph is formatted with a double border and shading.");
doc.Save(ArtifactsDir + "DocumentBuilder.ApplyBordersAndShading.docx");
```

### Se även

* class [Border](../../border/)
* enum [BorderType](../../bordertype/)
* class [BorderCollection](../)
* namnutrymme [Aspose.Words](../../bordercollection/)
* hopsättning [Aspose.Words](../../../)

---

## BorderCollection indexer (2 of 2)

Hämtar ett kantobjekt med index.

```csharp
public Border this[int index] { get; }
```

| Parameter | Beskrivning |
| --- | --- |
| index | Nollbaserat index för gränsen att hämta. |

### Exempel

Visar hur gränssamlingar kan dela element.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Paragraph 1.");
builder.Write("Paragraph 2.");

// Eftersom vi använde samma kantkonfiguration när vi skapade
// dessa stycken, deras gränssamlingar delar samma element.
BorderCollection firstParagraphBorders = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Borders;
BorderCollection secondParagraphBorders = builder.CurrentParagraph.ParagraphFormat.Borders;

for (int i = 0; i < firstParagraphBorders.Count; i++)
{
    Assert.IsTrue(firstParagraphBorders[i].Equals(secondParagraphBorders[i]));
    Assert.AreEqual(firstParagraphBorders[i].GetHashCode(), secondParagraphBorders[i].GetHashCode());
    Assert.False(firstParagraphBorders[i].IsVisible);
}

foreach (Border border in secondParagraphBorders)
    border.LineStyle = LineStyle.DotDash;

// Efter att ha ändrat linjestilen för kanterna i bara det andra stycket,
// gränssamlingarna delar inte längre samma element.
for (int i = 0; i < firstParagraphBorders.Count; i++)
{
    Assert.IsFalse(firstParagraphBorders[i].Equals(secondParagraphBorders[i]));
    Assert.AreNotEqual(firstParagraphBorders[i].GetHashCode(), secondParagraphBorders[i].GetHashCode());

    // Att ändra utseendet på en tom kant gör den synlig.
    Assert.True(secondParagraphBorders[i].IsVisible);
}

doc.Save(ArtifactsDir + "Border.SharedElements.docx");
```

### Se även

* class [Border](../../border/)
* class [BorderCollection](../)
* namnutrymme [Aspose.Words](../../bordercollection/)
* hopsättning [Aspose.Words](../../../)


