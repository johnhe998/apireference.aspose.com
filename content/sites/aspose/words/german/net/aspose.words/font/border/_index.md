---
title: Font.Border
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Gibt ein BorderObjekt zurück das den Rand für die Schriftart angibt.
type: docs
weight: 60
url: /de/net/aspose.words/font/border/
---
## Font.Border property

Gibt ein Border-Objekt zurück, das den Rand für die Schriftart angibt.

```csharp
public Border Border { get; }
```

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

* class [Border](../../border/)
* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


