---
title: Font.ClearFormatting
second_title: Aspose.Words für .NET-API-Referenz
description: Font methode. Setzt auf Standardschriftformatierung zurück.
type: docs
weight: 550
url: /de/net/aspose.words/font/clearformatting/
---
## Font.ClearFormatting method

Setzt auf Standardschriftformatierung zurück.

```csharp
public void ClearFormatting()
```

### Bemerkungen

Entfernt alle explizit für das Objekt angegebenen Schriftformatierungen von which  **Schriftart** abgerufen wurde, wird die Schriftartformatierung von dem entsprechenden übergeordneten Element geerbt.

### Beispiele

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

* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


