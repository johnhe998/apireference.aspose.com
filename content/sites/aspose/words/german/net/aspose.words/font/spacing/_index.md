---
title: Font.Spacing
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Gibt den Abstand in Punkten zwischen Zeichen zurück oder legt ihn fest .
type: docs
weight: 380
url: /de/net/aspose.words/font/spacing/
---
## Font.Spacing property

Gibt den Abstand (in Punkten) zwischen Zeichen zurück oder legt ihn fest .

```csharp
public double Spacing { get; set; }
```

### Beispiele

Zeigt, wie Sie die horizontale Skalierung und den Abstand für Zeichen festlegen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Textverlauf hinzufügen und Zeichenbreite auf 150 % erhöhen.
builder.Font.Scaling = 150;
builder.Writeln("Wide characters");

// Textverlauf hinzufügen und 1pt zusätzlichen horizontalen Abstand zwischen jedem Zeichen hinzufügen.
builder.Font.Spacing = 1;
builder.Writeln("Expanded by 1pt");

// Textverlauf hinzufügen und Zeichen um 1pt näher zusammenbringen.
builder.Font.Spacing = -1;
builder.Writeln("Condensed by 1pt");

doc.Save(ArtifactsDir + "Font.ScalingSpacing.docx");
```

### Siehe auch

* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


