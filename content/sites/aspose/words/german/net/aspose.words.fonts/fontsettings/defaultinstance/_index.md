---
title: FontSettings.DefaultInstance
second_title: Aspose.Words für .NET-API-Referenz
description: FontSettings eigendom. Statische Standardschrifteinstellungen.
type: docs
weight: 20
url: /de/net/aspose.words.fonts/fontsettings/defaultinstance/
---
## FontSettings.DefaultInstance property

Statische Standardschrifteinstellungen.

```csharp
public static FontSettings DefaultInstance { get; }
```

### Bemerkungen

Diese Instanz wird standardmäßig in einem Dokument verwendet, es sei denn[`FontSettings`](../../../aspose.words/document/fontsettings/) angegeben ist.

### Beispiele

Zeigt, wie die standardmäßige Schrifteinstellungsinstanz konfiguriert wird.

```csharp
// Konfigurieren Sie die Instanz der Standardschrifteinstellungen so, dass die Schriftart "Courier New" verwendet wird
// als Backup-Ersatz, wenn wir versuchen, eine unbekannte Schriftart zu verwenden.
FontSettings.DefaultInstance.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Courier New";

Assert.True(FontSettings.DefaultInstance.SubstitutionSettings.DefaultFontSubstitution.Enabled);

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Non-existent font";
builder.Write("Hello world!");

// Dieses Dokument hat keine FontSettings-Konfiguration. Wenn wir das Dokument rendern,
// Die standardmäßige FontSettings-Instanz löst die fehlende Schriftart auf.
// Aspose.Words verwendet "Courier New", um Text zu rendern, der die unbekannte Schriftart verwendet.
Assert.Null(doc.FontSettings);

doc.Save(ArtifactsDir + "FontSettings.DefaultFontInstance.pdf");
```

Zeigt, wie die IWarningCallback-Schnittstelle zum Überwachen von Schriftartersetzungswarnungen verwendet wird.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Font.Name = "Times New Roman";
    builder.Writeln("Hello world!");

    FontSubstitutionWarningCollector callback = new FontSubstitutionWarningCollector();
    doc.WarningCallback = callback;

    // Speichern Sie die aktuelle Sammlung von Schriftartquellen, die die Standardschriftquelle für jedes Dokument sein wird
    // für die wir keine andere Schriftartquelle angeben.
    FontSourceBase[] originalFontSources = FontSettings.DefaultInstance.GetFontsSources();

    // Zu Testzwecken werden wir Aspose.Words so einstellen, dass es nur in einem Ordner nach Schriftarten sucht, der nicht existiert.
    FontSettings.DefaultInstance.SetFontsFolder(string.Empty, false);

    // Beim Rendern des Dokuments gibt es keinen Platz, um die Schriftart "Times New Roman" zu finden.
    // Dies führt zu einer Schriftartersetzungswarnung, die unser Callback erkennt.
    doc.Save(ArtifactsDir + "FontSettings.SubstitutionWarning.pdf");

    FontSettings.DefaultInstance.SetFontsSources(originalFontSources);

    Assert.True(callback.FontSubstitutionWarnings[0].Description
        .Equals(
            "Font 'Times New Roman' has not been found. Using 'Fanwood' font instead. Reason: first available font."));
}

private class FontSubstitutionWarningCollector : IWarningCallback
{
    /// <summary>
    /// Wird jedes Mal aufgerufen, wenn während des Ladens/Speicherns eine Warnung auftritt.
    /// </summary>
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontSubstitutionWarnings.Warning(info);
    }

    public WarningInfoCollection FontSubstitutionWarnings = new WarningInfoCollection();
}
```

### Siehe auch

* class [FontSettings](../)
* namensraum [Aspose.Words.Fonts](../../fontsettings/)
* Montage [Aspose.Words](../../../)


