---
title: Font.Bidi
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Gibt an ob der Inhalt dieses Laufs von rechts nach links verlaufen soll.
type: docs
weight: 30
url: /de/net/aspose.words/font/bidi/
---
## Font.Bidi property

Gibt an, ob der Inhalt dieses Laufs von rechts nach links verlaufen soll.

```csharp
public bool Bidi { get; set; }
```

### Bemerkungen

Wenn diese Eigenschaft aktiviert ist, darf sie nicht mit stark von links nach rechts verlaufendem Text verwendet werden. Jedes Verhalten unter dieser Bedingung ist nicht spezifiziert. Wenn diese Eigenschaft deaktiviert ist, darf sie nicht mit starkem rechts-nach-links-Text verwendet werden. Jedes Verhalten unter dieser Bedingung ist nicht spezifiziert.

Wenn der Inhalt dieses Durchlaufs angezeigt wird, werden alle Zeichen für Formatierungszwecke als komplexe Schriftzeichen behandelt . Das bedeutet, dass[`BoldBi`](../boldbi/) ,[`ItalicBi`](../italicbi/) ,[`SizeBi`](../sizebi/) und ein entsprechender Schriftartname wird beim Rendern dieses Laufs verwendet.

Wenn der Inhalt dieses Laufs angezeigt wird, fungiert diese Eigenschaft außerdem als Überschreibung von rechts nach links für die Zeichen , die als "schwache Typen" und "neutrale Typen" klassifiziert sind.

### Beispiele

Zeigt, wie separate Sätze von Schriftarteinstellungen für rechts-nach-links- und rechts-nach-links-Text definiert werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Definieren Sie eine Reihe von Schriftarteinstellungen für von links nach rechts verlaufenden Text.
builder.Font.Name = "Courier New";
builder.Font.Size = 16;
builder.Font.Italic = false;
builder.Font.Bold = false;
builder.Font.LocaleId = new CultureInfo("en-US", false).LCID;

// Definieren Sie einen weiteren Satz von Schriftarteinstellungen für von rechts nach links verlaufenden Text.
builder.Font.NameBi = "Andalus";
builder.Font.SizeBi = 24;
builder.Font.ItalicBi = true;
builder.Font.BoldBi = true;
builder.Font.LocaleIdBi = new CultureInfo("ar-AR", false).LCID;

// Wir können das Bidi-Flag verwenden, um anzuzeigen, ob der Text hinzugefügt wird
// mit dem Document Builder ist von rechts nach links. Wenn wir Text hinzufügen, wobei dieses Flag auf „true“ gesetzt ist,
// es wird mit den Schriftarteinstellungen von rechts nach links formatiert.
builder.Font.Bidi = true;
builder.Write("مرحبًا");

// Setzen Sie das Flag auf false und fügen Sie dann Text von links nach rechts hinzu.
// Der Document Builder formatiert diese mit den Schriftarteinstellungen von links nach rechts.
builder.Font.Bidi = false;
builder.Write(" Hello world!");

doc.Save(ArtifactsDir + "Font.Bidi.docx");
```

### Siehe auch

* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


