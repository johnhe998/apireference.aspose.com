---
title: Font.Underline
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Ruft den auf die Schriftart angewendeten Unterstreichungstyp ab oder legt ihn fest.
type: docs
weight: 530
url: /de/net/aspose.words/font/underline/
---
## Font.Underline property

Ruft den auf die Schriftart angewendeten Unterstreichungstyp ab oder legt ihn fest.

```csharp
public Underline Underline { get; set; }
```

### Beispiele

Zeigt, wie Sie den Stil und die Farbe einer Textunterstreichung konfigurieren.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Underline = Underline.Dotted;
builder.Font.UnderlineColor = Color.Red;

builder.Writeln("Underlined text.");

doc.Save(ArtifactsDir + "Font.Underlines.docx");
```

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

Zeigt, wie ein Hyperlink-Feld eingefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("For more information, please visit the ");

// Hyperlink einfügen und mit benutzerdefinierter Formatierung hervorheben.
// Der Hyperlink ist ein anklickbares Textstück, das uns zu der in der URL angegebenen Stelle führt.
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;
builder.InsertHyperlink("Google website", "https://www.google.com", falsch);
builder.Font.ClearFormatting();
builder.Writeln(".");

// Strg + Linksklick auf den Link im Text in Microsoft Word bringt uns über ein neues Webbrowser-Fenster zur URL.
doc.Save(ArtifactsDir + "DocumentBuilder.InsertHyperlink.docx");
```

### Siehe auch

* enum [Underline](../../underline/)
* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


