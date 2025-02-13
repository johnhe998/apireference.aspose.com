---
title: Font.Kerning
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Ruft die Schriftgröße ab oder legt sie fest bei der Kerning beginnt.
type: docs
weight: 180
url: /de/net/aspose.words/font/kerning/
---
## Font.Kerning property

Ruft die Schriftgröße ab oder legt sie fest, bei der Kerning beginnt.

```csharp
public double Kerning { get; set; }
```

### Beispiele

Zeigt, wie die Schriftgröße angegeben wird, bei der Kerning wirksam wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial Black";

// Legen Sie die Schriftgröße des Builders und die Mindestgröße fest, bei der Kerning wirksam wird.
// Die Schriftgröße fällt unter den Kerning-Schwellenwert, sodass der Lauf unten kein Kerning hat.
builder.Font.Size = 18;
builder.Font.Kerning = 24;

builder.Writeln("TALLY. (Kerning not applied)");

// Stellen Sie den Kerning-Schwellenwert so ein, dass die aktuelle Schriftgröße des Builders darüber liegt.
// Auf jeden Text, den wir ab diesem Punkt hinzufügen, wird Kerning angewendet. Die Leerzeichen zwischen den Zeichen
// wird angepasst, was normalerweise zu einem etwas ästhetisch ansprechenderen Textlauf führt.
builder.Font.Kerning = 12;

builder.Writeln("TALLY. (Kerning applied)");

doc.Save(ArtifactsDir + "Font.Kerning.docx");
```

### Siehe auch

* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


