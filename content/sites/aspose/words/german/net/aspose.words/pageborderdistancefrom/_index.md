---
title: Enum PageBorderDistanceFrom
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.PageBorderDistanceFrom opsomming. Legt die Positionierung des Seitenrandes relativ zum Seitenrand fest.
type: docs
weight: 4110
url: /de/net/aspose.words/pageborderdistancefrom/
---
## PageBorderDistanceFrom enumeration

Legt die Positionierung des Seitenrandes relativ zum Seitenrand fest.

```csharp
public enum PageBorderDistanceFrom
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Text | `0` | Die Randposition wird vom Seitenrand aus gemessen. |
| PageEdge | `1` | Die Randposition wird vom Seitenrand aus gemessen. |

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

* class [PageSetup](../pagesetup/)
* property [BorderDistanceFrom](../pagesetup/borderdistancefrom/)
* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


