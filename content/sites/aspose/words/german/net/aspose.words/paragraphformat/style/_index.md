---
title: ParagraphFormat.Style
second_title: Aspose.Words für .NET-API-Referenz
description: ParagraphFormat eigendom. Ruft den auf diese Formatierung angewendeten Absatzstil ab oder legt ihn fest.
type: docs
weight: 330
url: /de/net/aspose.words/paragraphformat/style/
---
## ParagraphFormat.Style property

Ruft den auf diese Formatierung angewendeten Absatzstil ab oder legt ihn fest.

```csharp
public Style Style { get; set; }
```

### Beispiele

Zeigt, wie Sie ein Absatzformat mit Listenformatierung erstellen und verwenden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Einen benutzerdefinierten Absatzstil erstellen.
Style style = doc.Styles.Add(StyleType.Paragraph, "MyStyle1");
style.Font.Size = 24;
style.Font.Name = "Verdana";
style.ParagraphFormat.SpaceAfter = 12;

// Erstellen Sie eine Liste und stellen Sie sicher, dass die Absätze, die diesen Stil verwenden, diese Liste verwenden.
style.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDefault);
style.ListFormat.ListLevelNumber = 0;

// Den Absatzstil auf den aktuellen Absatz des Document Builder anwenden und dann etwas Text hinzufügen.
builder.ParagraphFormat.Style = style;
builder.Writeln("Hello World: MyStyle1, bulleted list.");

// Ändern Sie den Stil des Document Builder in einen Stil ohne Listenformatierung und schreiben Sie einen weiteren Absatz.
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln("Hello World: Normal.");

builder.Document.Save(ArtifactsDir + "Styles.ParagraphStyleBulletedList.docx");
```

### Siehe auch

* class [Style](../../style/)
* class [ParagraphFormat](../)
* namensraum [Aspose.Words](../../paragraphformat/)
* Montage [Aspose.Words](../../../)


