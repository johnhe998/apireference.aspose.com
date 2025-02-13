---
title: PageSetup.BorderAppliesTo
second_title: Aspose.Words für .NET-API-Referenz
description: PageSetup eigendom. Gibt an auf welchen Seiten der Seitenrand gedruckt wird.
type: docs
weight: 30
url: /de/net/aspose.words/pagesetup/borderappliesto/
---
## PageSetup.BorderAppliesTo property

Gibt an, auf welchen Seiten der Seitenrand gedruckt wird.

```csharp
public PageBorderAppliesTo BorderAppliesTo { get; set; }
```

### Beispiele

Zeigt, wie Sie oben auf der ersten Seite einen breiten blauen Rahmen erstellen.

```csharp
Document doc = new Document();

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.BorderAlwaysInFront = false;
pageSetup.BorderDistanceFrom = PageBorderDistanceFrom.PageEdge;
pageSetup.BorderAppliesTo = PageBorderAppliesTo.FirstPage;

Border border = pageSetup.Borders[BorderType.Top];
border.LineStyle = LineStyle.Single;
border.LineWidth = 30;
border.Color = Color.Blue;
border.DistanceFromText = 0;

doc.Save(ArtifactsDir + "PageSetup.PageBorderProperties.docx");
```

### Siehe auch

* enum [PageBorderAppliesTo](../../pageborderappliesto/)
* class [PageSetup](../)
* namensraum [Aspose.Words](../../pagesetup/)
* Montage [Aspose.Words](../../../)


