---
title: FontFallbackSettings.LoadMsOfficeFallbackSettings
second_title: Aspose.Words für .NET-API-Referenz
description: FontFallbackSettings methode. Lädt vordefinierte FallbackEinstellungen die das Fallback von Microsoft Word nachahmen und Microsoft OfficeSchriftarten verwenden.
type: docs
weight: 30
url: /de/net/aspose.words.fonts/fontfallbacksettings/loadmsofficefallbacksettings/
---
## FontFallbackSettings.LoadMsOfficeFallbackSettings method

Lädt vordefinierte Fallback-Einstellungen, die das Fallback von Microsoft Word nachahmen und Microsoft Office-Schriftarten verwenden.

```csharp
public void LoadMsOfficeFallbackSettings()
```

### Beispiele

Zeigt, wie vordefinierte Fallback-Schriftarteinstellungen geladen werden.

```csharp
Document doc = new Document();

FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;
FontFallbackSettings fontFallbackSettings = fontSettings.FallbackSettings;

// Speichern Sie das Standard-Fallback-Schriftschema in einem XML-Dokument.
// Zum Beispiel hat eines der Elemente einen Wert von "0C00-0C7F" für Range und einen entsprechenden "Vani"-Wert für FallbackFonts.
// Dies bedeutet, dass, wenn die Schriftart, die ein Text verwendet, keine Symbole für den Unicode-Block 0x0C00-0x0C7F enthält,
// Das Fallback-Schema verwendet Symbole aus dem Schriftersatz "Vani".
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettings.Default.xml");

// Unten sind zwei vordefinierte Font-Fallback-Schemata, aus denen wir wählen können.
// 1 - Verwenden Sie das standardmäßige Microsoft Office-Schema, das mit dem Standardschema identisch ist:
fontFallbackSettings.LoadMsOfficeFallbackSettings();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettings.LoadMsOfficeFallbackSettings.xml");

// 2 - Verwenden Sie das Schema, das aus Google Noto-Schriftarten erstellt wurde:
fontFallbackSettings.LoadNotoFallbackSettings();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettings.LoadNotoFallbackSettings.xml");
```

### Siehe auch

* class [FontFallbackSettings](../)
* namensraum [Aspose.Words.Fonts](../../fontfallbacksettings/)
* Montage [Aspose.Words](../../../)


