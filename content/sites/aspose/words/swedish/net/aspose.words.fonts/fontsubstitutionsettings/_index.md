---
title: Class FontSubstitutionSettings
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Fonts.FontSubstitutionSettings klass. Anger inställningar för teckensnittsersättningsmekanism.
type: docs
weight: 2830
url: /sv/net/aspose.words.fonts/fontsubstitutionsettings/
---
## FontSubstitutionSettings class

Anger inställningar för teckensnittsersättningsmekanism.

```csharp
public class FontSubstitutionSettings
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [DefaultFontSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/defaultfontsubstitution/) { get; } | Inställningar relaterade till standardregel för teckensnittsersättning. |
| [FontConfigSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/fontconfigsubstitution/) { get; } | Inställningar relaterade till regel för teckensnittskonfigurationsersättning. |
| [FontInfoSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/fontinfosubstitution/) { get; } | Inställningar relaterade till regel för ersättning av teckensnittsinformation. |
| [FontNameSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/fontnamesubstitution/) { get; } | Inställningar relaterade till regel för teckensnittsnamnsersättning. |
| [TableSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/tablesubstitution/) { get; } | Inställningar relaterade till regel för tabellersättning. |

### Anmärkningar

Teckensnittsersättningsprocessen består av flera regler som kontrolleras en efter en i specifik ordning. Om den första regeln inte kan lösa teckensnittet så kontrolleras den andra regeln och så vidare.

Ordningen på reglerna är följande: 1. Regel för ersättning av teckensnittsnamn (aktiverad som standard) 2. Regel för ersättning av teckensnittskonfiguration (inaktiverad som standard) 3. Regel för tabellersättning (aktiverad som standard) 4. Regel för ersättning av teckensnittsinformation (aktiverad som standard) 5. Standard teckensnittsregel (aktiverad som standard)

Observera att regeln för ersättning av teckensnittsinformation alltid kommer att lösa teckensnittet if[`FontInfo`](../fontinfo/) är available och kommer att åsidosätta standardfontregeln. Om du vill använda standardfontregeln bör du inaktivera regeln för ersättning av typsnittsinformation .

Observera att ersättningsregeln för teckensnittskonfiguration kommer att lösa teckensnittet i de flesta fall och åsidosätter därmed alla andra regler.

### Exempel

Visar hur du kommer åt ett dokuments systemteckensnittskälla och ställer in teckensnittsersättningar.

```csharp
Document doc = new Document();
doc.FontSettings = new FontSettings();

// Som standard innehåller ett tomt dokument alltid en systemfontkälla.
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

// Ställ in ett teckensnitt som finns i Windows Fonts-katalogen som ett substitut för ett som inte gör det.
doc.FontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = true;
doc.FontSettings.SubstitutionSettings.TableSubstitution.AddSubstitutes("Kreon-Regular", new[] {"Calibri"});

Assert.AreEqual(1,
    doc.FontSettings.SubstitutionSettings.TableSubstitution.GetSubstitutes("Kreon-Regular").Count());
Assert.Contains("Calibri",
    doc.FontSettings.SubstitutionSettings.TableSubstitution.GetSubstitutes("Kreon-Regular").ToArray());

// Alternativt kan vi lägga till en mappfontkälla där motsvarande mapp innehåller typsnittet.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false);
doc.FontSettings.SetFontsSources(new FontSourceBase[] {systemFontSource, folderFontSource});
Assert.AreEqual(2, doc.FontSettings.GetFontsSources().Length);

// Att återställa teckensnittskällorna lämnar oss fortfarande kvar med systemteckensnittskällan såväl som våra substitut.
doc.FontSettings.ResetFontSources();

Assert.AreEqual(1, doc.FontSettings.GetFontsSources().Length);
Assert.AreEqual(FontSourceType.SystemFonts, doc.FontSettings.GetFontsSources()[0].Type);
Assert.AreEqual(1,
    doc.FontSettings.SubstitutionSettings.TableSubstitution.GetSubstitutes("Kreon-Regular").Count());
```

### Se även

* namnutrymme [Aspose.Words.Fonts](../../aspose.words.fonts/)
* hopsättning [Aspose.Words](../../)


