---
title: Enum Orientation
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Orientation opsomming. Gibt die Seitenausrichtung an.
type: docs
weight: 4080
url: /de/net/aspose.words/orientation/
---
## Orientation enumeration

Gibt die Seitenausrichtung an.

```csharp
public enum Orientation
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Portrait | `1` | Seitenausrichtung im Hochformat (schmal und hoch). |
| Landscape | `2` | Seitenausrichtung im Querformat (breit und kurz). |

### Beispiele

Zeigt, wie Seiteneinrichtungseinstellungen auf Abschnitte in einem Dokument angewendet und zurückgesetzt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ändern Sie die Seiteneinrichtungseigenschaften für den aktuellen Abschnitt des Builders und fügen Sie Text hinzu.
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.VerticalAlignment = PageVerticalAlignment.Center;
builder.Writeln("This is the first section, which landscape oriented with vertically centered text.");

// Wenn wir mit einem Document Builder einen neuen Abschnitt beginnen,
// er erbt die aktuellen Seiteneinrichtungseigenschaften des Builders.
builder.InsertBreak(BreakType.SectionBreakNewPage);

Assert.AreEqual(Orientation.Landscape, doc.Sections[1].PageSetup.Orientation);
Assert.AreEqual(PageVerticalAlignment.Center, doc.Sections[1].PageSetup.VerticalAlignment);

// Wir können die Seiteneinrichtungseigenschaften mit der Methode "ClearFormatting" auf ihre Standardwerte zurücksetzen.
builder.PageSetup.ClearFormatting();

Assert.AreEqual(Orientation.Portrait, doc.Sections[1].PageSetup.Orientation);
Assert.AreEqual(PageVerticalAlignment.Top, doc.Sections[1].PageSetup.VerticalAlignment);

builder.Writeln("This is the second section, which is in default Letter paper size, portrait orientation and top alignment.");

doc.Save(ArtifactsDir + "PageSetup.ClearFormatting.docx");
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


