---
title: Font.Bold
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Wahr wenn die Schriftart fett formatiert ist.
type: docs
weight: 40
url: /de/net/aspose.words/font/bold/
---
## Font.Bold property

Wahr, wenn die Schriftart fett formatiert ist.

```csharp
public bool Bold { get; set; }
```

### Beispiele

Zeigt, wie formatierter Text mit DocumentBuilder eingefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Schriftartformatierung angeben, dann Text hinzufügen.
Aspose.Words.Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Courier New";
font.Underline = Underline.Dash;

builder.Write("Hello world!");
```

### Siehe auch

* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


