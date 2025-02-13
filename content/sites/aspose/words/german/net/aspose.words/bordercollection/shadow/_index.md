---
title: BorderCollection.Shadow
second_title: Aspose.Words für .NET-API-Referenz
description: BorderCollection eigendom. Ruft einen Wert ab oder legt einen Wert fest der angibt ob der Rahmen einen Schatten hat.
type: docs
weight: 110
url: /de/net/aspose.words/bordercollection/shadow/
---
## BorderCollection.Shadow property

Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob der Rahmen einen Schatten hat.

```csharp
public bool Shadow { get; set; }
```

### Bemerkungen

Ruft den Wert vom ersten Rahmen in der Auflistung ab.

Legt den Wert für alle Ränder in der Sammlung außer diagonalen Rändern fest.

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


