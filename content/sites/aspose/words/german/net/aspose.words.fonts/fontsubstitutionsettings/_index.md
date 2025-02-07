---
title: Class FontSubstitutionSettings
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Fonts.FontSubstitutionSettings klas. Gibt die Einstellungen des Schriftartersetzungsmechanismus an.
type: docs
weight: 2830
url: /de/net/aspose.words.fonts/fontsubstitutionsettings/
---
## FontSubstitutionSettings class

Gibt die Einstellungen des Schriftartersetzungsmechanismus an.

```csharp
public class FontSubstitutionSettings
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [DefaultFontSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/defaultfontsubstitution/) { get; } | Einstellungen im Zusammenhang mit der Standardschriftersetzungsregel. |
| [FontConfigSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/fontconfigsubstitution/) { get; } | Einstellungen im Zusammenhang mit der Schriftkonfigurations-Ersetzungsregel. |
| [FontInfoSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/fontinfosubstitution/) { get; } | Einstellungen im Zusammenhang mit der Ersetzungsregel für Schriftinformationen. |
| [FontNameSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/fontnamesubstitution/) { get; } | Einstellungen im Zusammenhang mit der Ersetzungsregel für Schriftnamen. |
| [TableSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/tablesubstitution/) { get; } | Einstellungen in Bezug auf die Tabellenersetzungsregel. |

### Bemerkungen

Der Font-Ersetzungsprozess besteht aus mehreren Regeln, die nacheinander in einer bestimmten Reihenfolge überprüft werden. Wenn die erste Regel den Font nicht auflösen kann, wird die zweite Regel überprüft und so weiter.

Die Reihenfolge der Regeln ist wie folgt: 1. Schriftnamen-Ersetzungsregel (standardmäßig aktiviert) 2. Schriftkonfigurations-Ersetzungsregel (standardmäßig deaktiviert) 3. Tabellenersetzungsregel (standardmäßig aktiviert) 4. Schriftinformationen-Ersetzungsregel (standardmäßig aktiviert) 5. Standardschriftregel (standardmäßig aktiviert)

Beachten Sie, dass die Font-Info-Ersetzungsregel immer den Font auflöst, wenn[`FontInfo`](../fontinfo/) ist available und überschreibt die Standardschriftregel. Wenn Sie die Standard-Schriftartregel verwenden möchten, sollten Sie die Regel zum Ersetzen der Schriftinformationen deaktivieren.

Beachten Sie, dass die Schriftkonfigurations-Ersetzungsregel die Schrift in den meisten Fällen auflöst und somit alle anderen Regeln außer Kraft setzt.

### Beispiele

Zeigt, wie Sie auf die Systemschriftquelle eines Dokuments zugreifen und Schriftartersatz festlegen.

```csharp
Document doc = new Document();
doc.FontSettings = new FontSettings();

// Standardmäßig enthält ein leeres Dokument immer eine Systemschriftquelle.
Assert.AreEqual(1, doc.FontSettings.GetFontsSources().Length);

SystemFontSource systemFontSource = (SystemFontSource) doc.FontSettings.GetFontsSources()[0];
Assert.AreEqual(FontSourceType.SystemFonts, systemFontSource.Type);
Assert.AreEqual(0, systemFontSource.Priority);

PlatformID pid = Environment.OSVersion.Platform;
bool isWindows = (pid == PlatformID.Win32NT) || (pid == PlatformID.Win32S) ||
                 (pid == PlatformID.Win32Windows) || (pid == PlatformID.WinCE);
if (isWindows)
{
    const string fontsPath = @"C:\WINDOWS\Fonts";
    Assert.AreEqual(fontsPath.ToLower(),
        SystemFontSource.GetSystemFontFolders().FirstOrDefault()?.ToLower());
}

foreach (string systemFontFolder in SystemFontSource.GetSystemFontFolders())
{
    Console.WriteLine(systemFontFolder);
}

// Festlegen einer im Windows Fonts-Verzeichnis vorhandenen Schriftart als Ersatz für eine nicht vorhandene Schriftart.
doc.FontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = true;
doc.FontSettings.SubstitutionSettings.TableSubstitution.AddSubstitutes("Kreon-Regular", new[] {"Calibri"});

Assert.AreEqual(1,
    doc.FontSettings.SubstitutionSettings.TableSubstitution.GetSubstitutes("Kreon-Regular").Count());
Assert.Contains("Calibri",
    doc.FontSettings.SubstitutionSettings.TableSubstitution.GetSubstitutes("Kreon-Regular").ToArray());

// Alternativ könnten wir einen Ordner font source hinzufügen, in dem der entsprechende Ordner die Schriftart enthält.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false);
doc.FontSettings.SetFontsSources(new FontSourceBase[] {systemFontSource, folderFontSource});
Assert.AreEqual(2, doc.FontSettings.GetFontsSources().Length);

// Das Zurücksetzen der Schriftartquellen lässt uns immer noch die Systemschriftquelle sowie unsere Ersatzquellen.
doc.FontSettings.ResetFontSources();

Assert.AreEqual(1, doc.FontSettings.GetFontsSources().Length);
Assert.AreEqual(FontSourceType.SystemFonts, doc.FontSettings.GetFontsSources()[0].Type);
Assert.AreEqual(1,
    doc.FontSettings.SubstitutionSettings.TableSubstitution.GetSubstitutes("Kreon-Regular").Count());
```

### Siehe auch

* namensraum [Aspose.Words.Fonts](../../aspose.words.fonts/)
* Montage [Aspose.Words](../../)


