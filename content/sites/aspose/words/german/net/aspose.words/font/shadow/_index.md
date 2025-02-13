---
title: Font.Shadow
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Wahr wenn die Schriftart als schattiert formatiert ist.
type: docs
weight: 330
url: /de/net/aspose.words/font/shadow/
---
## Font.Shadow property

Wahr, wenn die Schriftart als schattiert formatiert ist.

```csharp
public bool Shadow { get; set; }
```

### Beispiele

Zeigt, wie Sie einen Textverlauf erstellen, der mit einem Schatten formatiert ist.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Setzen Sie das Schatten-Flag, um einen Offset-Schatteneffekt anzuwenden,
// es so aussehen lässt, als würden die Buchstaben über der Seite schweben.
builder.Font.Shadow = true;
builder.Font.Size = 36;

builder.Writeln("This text has a shadow.");

doc.Save(ArtifactsDir + "Font.Shadow.docx");
```

### Siehe auch

* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


