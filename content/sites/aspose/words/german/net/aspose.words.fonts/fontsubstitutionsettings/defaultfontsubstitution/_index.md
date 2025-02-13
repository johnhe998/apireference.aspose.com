---
title: FontSubstitutionSettings.DefaultFontSubstitution
second_title: Aspose.Words für .NET-API-Referenz
description: FontSubstitutionSettings eigendom. Einstellungen im Zusammenhang mit der Standardschriftersetzungsregel.
type: docs
weight: 10
url: /de/net/aspose.words.fonts/fontsubstitutionsettings/defaultfontsubstitution/
---
## FontSubstitutionSettings.DefaultFontSubstitution property

Einstellungen im Zusammenhang mit der Standardschriftersetzungsregel.

```csharp
public DefaultFontSubstitutionRule DefaultFontSubstitution { get; }
```

### Beispiele

Zeigt, wie die Standardschriftersetzungsregel festgelegt wird.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// Holen Sie sich die Standard-Ersetzungsregel in FontSettings.
// Diese Regel ersetzt alle fehlenden Schriftarten durch "Times New Roman".
DefaultFontSubstitutionRule defaultFontSubstitutionRule =
    fontSettings.SubstitutionSettings.DefaultFontSubstitution;
Assert.True(defaultFontSubstitutionRule.Enabled);
Assert.AreEqual("Times New Roman", defaultFontSubstitutionRule.DefaultFontName);

// Stellen Sie den Ersatz für die Standardschriftart auf "Courier New" ein.
defaultFontSubstitutionRule.DefaultFontName = "Courier New";

// Fügen Sie mit einem Document Builder Text in einer Schriftart hinzu, die wir nicht sehen müssen, damit die Ersetzung stattfindet,
// und dann das Ergebnis in ein PDF rendern.
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Missing Font";
builder.Writeln("Line written in a missing font, which will be substituted with Courier New.");

doc.Save(ArtifactsDir + "FontSettings.DefaultFontSubstitutionRule.pdf");
```

### Siehe auch

* class [DefaultFontSubstitutionRule](../../defaultfontsubstitutionrule/)
* class [FontSubstitutionSettings](../)
* namensraum [Aspose.Words.Fonts](../../fontsubstitutionsettings/)
* Montage [Aspose.Words](../../../)


