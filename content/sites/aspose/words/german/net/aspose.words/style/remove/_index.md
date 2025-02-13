---
title: Style.Remove
second_title: Aspose.Words für .NET-API-Referenz
description: Style methode. Entfernt den angegebenen Stil aus dem Dokument.
type: docs
weight: 180
url: /de/net/aspose.words/style/remove/
---
## Style.Remove method

Entfernt den angegebenen Stil aus dem Dokument.

```csharp
public void Remove()
```

### Bemerkungen

Das Entfernen des Stils hat folgende Auswirkungen auf das Dokumentmodell:

* Alle Verweise auf den Stil werden aus entsprechenden Absätzen, Läufen und Tabellen entfernt.
* Wenn der Basisstil entfernt wird, wird seine Formatierung in untergeordnete Stile verschoben.
* Wenn der zu löschende Stil einen verknüpften Stil hat, werden beide gelöscht.

### Beispiele

Zeigt, wie Sie einen benutzerdefinierten Stil erstellen und anwenden.

```csharp
Document doc = new Document();

Style style = doc.Styles.Add(StyleType.Paragraph, "MyStyle");
style.Font.Name = "Times New Roman";
style.Font.Size = 16;
style.Font.Color = Color.Navy;

DocumentBuilder builder = new DocumentBuilder(doc);

// Einen der Stile aus dem Dokument auf den Absatz anwenden, den der Document Builder erstellt.
builder.ParagraphFormat.Style = doc.Styles["MyStyle"];
builder.Writeln("Hello world!");

Style firstParagraphStyle = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Style;

Assert.AreEqual(style, firstParagraphStyle);

// Unseren benutzerdefinierten Stil aus der Stilsammlung des Dokuments entfernen.
doc.Styles["MyStyle"].Remove();

firstParagraphStyle = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Style;

// Jeder Text, der einen entfernten Stil verwendet hat, wird auf die Standardformatierung zurückgesetzt.
Assert.False(doc.Styles.Any(s => s.Name == "MyStyle"));
Assert.AreEqual("Times New Roman", firstParagraphStyle.Font.Name);
Assert.AreEqual(12.0d, firstParagraphStyle.Font.Size);
Assert.AreEqual(Color.Empty.ToArgb(), firstParagraphStyle.Font.Color.ToArgb());
```

### Siehe auch

* class [Style](../)
* namensraum [Aspose.Words](../../style/)
* Montage [Aspose.Words](../../../)


