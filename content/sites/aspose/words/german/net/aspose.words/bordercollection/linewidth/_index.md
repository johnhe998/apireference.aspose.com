---
title: BorderCollection.LineWidth
second_title: Aspose.Words für .NET-API-Referenz
description: BorderCollection eigendom. Liest oder setzt die Rahmenbreite in Punkt.
type: docs
weight: 90
url: /de/net/aspose.words/bordercollection/linewidth/
---
## BorderCollection.LineWidth property

Liest oder setzt die Rahmenbreite in Punkt.

```csharp
public double LineWidth { get; set; }
```

### Bemerkungen

Gibt die Breite des ersten Rahmens in der Sammlung zurück.

Legt die Breite aller Rahmen in der Sammlung mit Ausnahme diagonaler Rahmen fest.

### Beispiele

Zeigt, wie Sie einen grünen wellenförmigen Seitenrand mit einem Schatten erstellen.

```csharp
Document doc = new Document();
PageSetup pageSetup = doc.Sections[0].PageSetup;

pageSetup.Borders.LineStyle = LineStyle.DoubleWave;
pageSetup.Borders.LineWidth = 2;
pageSetup.Borders.Color = Color.Green;
pageSetup.Borders.DistanceFromText = 24;
pageSetup.Borders.Shadow = true;

doc.Save(ArtifactsDir + "PageSetup.PageBorders.docx");
```

### Siehe auch

* class [BorderCollection](../)
* namensraum [Aspose.Words](../../bordercollection/)
* Montage [Aspose.Words](../../../)


