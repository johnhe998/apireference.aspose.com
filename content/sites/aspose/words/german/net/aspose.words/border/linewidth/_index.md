---
title: Border.LineWidth
second_title: Aspose.Words für .NET-API-Referenz
description: Border eigendom. Liest oder setzt die Rahmenbreite in Punkt.
type: docs
weight: 50
url: /de/net/aspose.words/border/linewidth/
---
## Border.LineWidth property

Liest oder setzt die Rahmenbreite in Punkt.

```csharp
public double LineWidth { get; set; }
```

### Bemerkungen

Wenn Sie die Linienbreite größer als null einstellen, wenn der Linienstil None ist, wird der Linienstil automatisch in eine einzelne Linie geändert.

### Beispiele

Zeigt, wie eine von einem Rahmen umgebene Zeichenfolge in ein Dokument eingefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Border.Color = Color.Green;
builder.Font.Border.LineWidth = 2.5d;
builder.Font.Border.LineStyle = LineStyle.DashDotStroker;

builder.Write("Text surrounded by green border.");

doc.Save(ArtifactsDir + "Border.FontBorder.docx");
```

### Siehe auch

* class [Border](../)
* namensraum [Aspose.Words](../../border/)
* Montage [Aspose.Words](../../../)


