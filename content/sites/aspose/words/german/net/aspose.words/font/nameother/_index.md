---
title: Font.NameOther
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Gibt die für Zeichen mit Zeichencodes von 128 bis 255 verwendete Schriftart zurück oder legt sie fest.
type: docs
weight: 270
url: /de/net/aspose.words/font/nameother/
---
## Font.NameOther property

Gibt die für Zeichen mit Zeichencodes von 128 bis 255 verwendete Schriftart zurück oder legt sie fest.

```csharp
public string NameOther { get; set; }
```

### Beispiele

Zeigt, wie Microsoft Word zwei verschiedene Schriftarten in einem Durchlauf kombinieren kann.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Stellen Sie sich einen Lauf vor, den wir mit dem Builder einfügen, während wir diese Schriftartkonfiguration verwenden
// enthält Zeichen innerhalb des ASCII-Zeichenbereichs. In diesem Fall,
// es zeigt diese Zeichen mit dieser Schriftart an.
builder.Font.NameAscii = "Calibri";

// Wenn keine andere Schriftart angegeben ist, wendet der Builder diese Schriftart auch auf alle Zeichen an, die er einfügt.
Assert.AreEqual("Calibri", builder.Font.Name);

// Geben Sie eine Schriftart an, die für alle Zeichen außerhalb des ASCII-Bereichs verwendet werden soll.
// Idealerweise sollte diese Schriftart eine Glyphe für jeden erforderlichen Nicht-ASCII-Zeichencode haben.
builder.Font.NameOther = "Courier New";

// Einfügen eines Laufs mit einem Wort bestehend aus ASCII-Zeichen und einem Wort mit allen Zeichen außerhalb dieses Bereichs.
// Jedes Zeichen wird abhängig von einer der Schriftarten angezeigt.
builder.Writeln("Hello, Привет");

doc.Save(ArtifactsDir + "Font.NameAscii.docx");
```

### Siehe auch

* property [Name](../name/)
* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


