---
title: BorderCollection.Item
second_title: Aspose.Words für .NET-API-Referenz
description: BorderCollection eigendom. Ruft ein Rahmenobjekt nach Rahmentyp ab.
type: docs
weight: 60
url: /de/net/aspose.words/bordercollection/item/
---
## BorderCollection indexer (1 of 2)

Ruft ein Rahmenobjekt nach Rahmentyp ab.

```csharp
public Border this[BorderType borderType] { get; }
```

| Parameter | Beschreibung |
| --- | --- |
| borderType | EIN[`BorderType`](../../bordertype/) value , der den Typ des abzurufenden Rahmens angibt. |

### Bemerkungen

Beachten Sie, dass nicht alle Rahmen für verschiedene Dokumentelemente vorhanden sind. Diese Methode löst eine Ausnahme aus, wenn Sie einen Rahmen anfordern, der für das aktuelle Objekt nicht anwendbar ist.

### Beispiele

Zeigt, wie Text mit Rändern und Schattierungen verziert wird.

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

### Siehe auch

* class [Border](../../border/)
* enum [BorderType](../../bordertype/)
* class [BorderCollection](../)
* namensraum [Aspose.Words](../../bordercollection/)
* Montage [Aspose.Words](../../../)

---

## BorderCollection indexer (2 of 2)

Ruft ein Border-Objekt nach Index ab.

```csharp
public Border this[int index] { get; }
```

| Parameter | Beschreibung |
| --- | --- |
| index | Nullbasierter Index der abzurufenden Grenze. |

### Beispiele

Zeigt, wie Rahmensammlungen Elemente gemeinsam nutzen können.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Paragraph 1.");
builder.Write("Paragraph 2.");

// Da wir beim Erstellen dieselbe Randkonfiguration verwendet haben
// Diese Absätze und ihre Randsammlungen teilen dieselben Elemente.
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

// Nachdem Sie den Linienstil der Rahmen nur im zweiten Absatz geändert haben,
// Die Randsammlungen haben nicht mehr die gleichen Elemente.
for (int i = 0; i < firstParagraphBorders.Count; i++)
{
    Assert.IsFalse(firstParagraphBorders[i].Equals(secondParagraphBorders[i]));
    Assert.AreNotEqual(firstParagraphBorders[i].GetHashCode(), secondParagraphBorders[i].GetHashCode());

    // Das Ändern des Aussehens eines leeren Rahmens macht ihn sichtbar.
    Assert.True(secondParagraphBorders[i].IsVisible);
}

doc.Save(ArtifactsDir + "Border.SharedElements.docx");
```

### Siehe auch

* class [Border](../../border/)
* class [BorderCollection](../)
* namensraum [Aspose.Words](../../bordercollection/)
* Montage [Aspose.Words](../../../)


