---
title: Document.FontSettings
second_title: Aspose.Words für .NET-API-Referenz
description: Document eigendom. Ruft Schrifteinstellungen für Dokumente ab oder legt sie fest.
type: docs
weight: 140
url: /de/net/aspose.words/document/fontsettings/
---
## Document.FontSettings property

Ruft Schrifteinstellungen für Dokumente ab oder legt sie fest.

```csharp
public FontSettings FontSettings { get; set; }
```

### Bemerkungen

Diese Eigenschaft ermöglicht die Angabe von Schriftarteinstellungen pro Dokument. Wenn auf null gesetzt, standardmäßige statische Schriftart settings [`DefaultInstance`](../../../aspose.words.fonts/fontsettings/defaultinstance/) wird verwendet.

Der Standardwert ist null.

### Beispiele

Zeigt, wie Schriftersetzungsregeln festgelegt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Amethysta";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

FontSourceBase[] fontSources = FontSettings.DefaultInstance.GetFontsSources();

// Die Standardschriftquellen enthalten die erste Schriftart, die das Dokument verwendet.
Assert.AreEqual(1, fontSources.Length);
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));

// Die zweite Schriftart, "Amethysta", ist nicht verfügbar.
Assert.False(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));

// Wir können eine Font-Ersetzungstabelle konfigurieren, die bestimmt
// welche Schriftarten Aspose.Words als Ersatz für nicht verfügbare Schriftarten verwendet.
// Legen Sie zwei Ersatzschriftarten für "Amethysta" fest: "Arvo" und "Courier New".
// Wenn der erste Ersatz nicht verfügbar ist, versucht Aspose.Words, den zweiten Ersatz zu verwenden, und so weiter.
doc.FontSettings = new FontSettings();
doc.FontSettings.SubstitutionSettings.TableSubstitution.SetSubstitutes(
    "Amethysta", new[] {"Arvo", "Courier New"});

 // "Amethysta" ist nicht verfügbar, und die Ersetzungsregel besagt, dass die erste als Ersatz zu verwendende Schriftart "Arvo" ist.
Assert.False(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

 // „Arvo“ ist ebenfalls nicht verfügbar, „Courier New“ hingegen schon.
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Courier New"));

// Das Ausgabedokument zeigt den Text mit der Schriftart "Amethysta" formatiert mit "Courier New" an.
doc.Save(ArtifactsDir + "FontSettings.TableSubstitution.pdf");
```

### Siehe auch

* class [FontSettings](../../../aspose.words.fonts/fontsettings/)
* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)


