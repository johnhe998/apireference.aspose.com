---
title: Font.Style
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Ruft den auf diese Formatierung angewendeten Zeichenstil ab oder legt ihn fest.
type: docs
weight: 400
url: /de/net/aspose.words/font/style/
---
## Font.Style property

Ruft den auf diese Formatierung angewendeten Zeichenstil ab oder legt ihn fest.

```csharp
public Style Style { get; set; }
```

### Beispiele

Wendet eine doppelte Unterstreichung auf alle Läufe in einem Dokument an, die mit benutzerdefinierten Zeichenstilen formatiert sind.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie einen benutzerdefinierten Stil ein und wenden Sie ihn auf Text an, der mit einem Document Builder erstellt wurde.
Style style = doc.Styles.Add(StyleType.Character, "MyStyle");
style.Font.Color = Color.Red;
style.Font.Name = "Courier New";

builder.Font.StyleName = "MyStyle";
builder.Write("This text is in a custom style.");

// Iteriere über jeden Lauf und füge jedem benutzerdefinierten Stil eine doppelte Unterstreichung hinzu.
foreach (Run run in doc.GetChildNodes(NodeType.Run, true).OfType<Run>())
{
    Style charStyle = run.Font.Style;

    if (!charStyle.BuiltIn)
        run.Font.Underline = Underline.Double;
}

doc.Save(ArtifactsDir + "Font.Style.docx");
```

### Siehe auch

* class [Style](../../style/)
* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


