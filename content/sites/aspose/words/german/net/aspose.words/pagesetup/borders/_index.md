---
title: PageSetup.Borders
second_title: Aspose.Words für .NET-API-Referenz
description: PageSetup eigendom. Ruft eine Sammlung der Seitenränder ab.
type: docs
weight: 50
url: /de/net/aspose.words/pagesetup/borders/
---
## PageSetup.Borders property

Ruft eine Sammlung der Seitenränder ab.

```csharp
public BorderCollection Borders { get; }
```

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

* class [BorderCollection](../../bordercollection/)
* class [PageSetup](../)
* namensraum [Aspose.Words](../../pagesetup/)
* Montage [Aspose.Words](../../../)


