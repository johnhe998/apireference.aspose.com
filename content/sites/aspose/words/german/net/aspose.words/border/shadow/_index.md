---
title: Border.Shadow
second_title: Aspose.Words für .NET-API-Referenz
description: Border eigendom. Ruft einen Wert ab oder legt einen Wert fest der angibt ob der Rahmen einen Schatten hat.
type: docs
weight: 60
url: /de/net/aspose.words/border/shadow/
---
## Border.Shadow property

Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob der Rahmen einen Schatten hat.

```csharp
public bool Shadow { get; set; }
```

### Bemerkungen

Damit ein Rahmen in Microsoft Word einen Schatten hat, müssen die Rahmen auf allen vier Seiten (links, oben, rechts und unten) denselben Typ, dieselbe Breite und dieselbe Farbe haben, und alle sollten die Shadow-Eigenschaft auf true gesetzt haben.

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

* class [Border](../)
* namensraum [Aspose.Words](../../border/)
* Montage [Aspose.Words](../../../)


