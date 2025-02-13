---
title: Font.Emboss
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Wahr wenn die Schriftart geprägt formatiert ist.
type: docs
weight: 100
url: /de/net/aspose.words/font/emboss/
---
## Font.Emboss property

Wahr, wenn die Schriftart geprägt formatiert ist.

```csharp
public bool Emboss { get; set; }
```

### Beispiele

Zeigt, wie Gravur-/Prägeeffekte auf Text angewendet werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 36;
builder.Font.Color = Color.LightBlue;

// Im Folgenden finden Sie zwei Möglichkeiten, Schatten zu verwenden, um einen 3D-ähnlichen Effekt auf den Text anzuwenden.
// 1 - Gravieren Sie Text, damit es so aussieht, als wären die Buchstaben in der Seite versunken:
builder.Font.Engrave = true;

builder.Writeln("This text is engraved.");

// 2 - Text prägen, damit es so aussieht, als würden die Buchstaben aus der Seite herausspringen:
builder.Font.Engrave = false;
builder.Font.Emboss = true;

builder.Writeln("This text is embossed.");

doc.Save(ArtifactsDir + "Font.EngraveEmboss.docx");
```

### Siehe auch

* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


