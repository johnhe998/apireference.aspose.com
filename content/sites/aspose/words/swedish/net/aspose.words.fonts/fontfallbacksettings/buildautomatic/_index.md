---
title: FontFallbackSettings.BuildAutomatic
second_title: Aspose.Words för .NET API Referens
description: FontFallbackSettings metod. Skapar automatiskt reservinställningarna genom att skanna tillgängliga teckensnitt.
type: docs
weight: 10
url: /sv/net/aspose.words.fonts/fontfallbacksettings/buildautomatic/
---
## FontFallbackSettings.BuildAutomatic method

Skapar automatiskt reservinställningarna genom att skanna tillgängliga teckensnitt.

```csharp
public void BuildAutomatic()
```

### Anmärkningar

Den här metoden kan ge icke-optimala reservinställningar. Teckensnitt kontrolleras av[ Unicode-teckenintervall](https://docs.microsoft.com/en-us/typography/opentype/spec/os2#ur) fält och inte av den faktiska närvaron av glyfer. Unicode-intervall kontrolleras också individuellt och flera intervall relaterade till ett enda språk/skript kan använda olika reservteckensnitt.

### Exempel

Visar hur man distribuerar reservteckensnitt över Unicode-teckenkodintervall.

```csharp
Document doc = new Document();

FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;
FontFallbackSettings fontFallbackSettings = fontSettings.FallbackSettings;

// Konfigurera våra teckensnittsinställningar till att endast källtypsnitt från mappen "MyFonts".
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false);
fontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

// Att anropa "BuildAutomatic"-metoden kommer att generera ett reservschema som
// distribuerar tillgängliga typsnitt över så många Unicode-teckenkoder som möjligt.
// I vårt fall har den bara tillgång till en handfull typsnitt i mappen "MyFonts".
fontFallbackSettings.BuildAutomatic();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettingsCustom.BuildAutomatic.xml");

// Vi kan också ladda ett anpassat ersättningsschema från en fil som denna.
// Detta schema tillämpar typsnittet "AllegroOpen" över "0000-00ff" Unicode-blocken, "AllegroOpen"-teckensnittet över "0100-024f",
// och typsnittet "M+ 2m" i alla andra intervall som andra typsnitt i schemat inte täcker.
fontFallbackSettings.Load(MyDir + "Custom font fallback settings.xml");

// Skapa en dokumentbyggare och ställ in dess teckensnitt till ett som inte finns i någon av våra källor.
// Våra teckensnittsinställningar kommer att anropa reservschemat för tecken som vi skriver med det otillgängliga teckensnittet.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Missing Font";

// Använd byggaren för att skriva ut varje Unicode-tecken från 0x0021 till 0x052F,
// med beskrivande linjer som delar Unicode-block som vi definierade i vårt anpassade typsnittsalternativ.
for (int i = 0x0021; i < 0x0530; i++)
{
    switch (i)
    {
        case 0x0021:
            builder.Writeln(
                "\n\n0x0021 - 0x00FF: \nBasic Latin/Latin-1 Supplement Unicode blocks in \"AllegroOpen\" font:");
            break;
        case 0x0100:
            builder.Writeln(
                "\n\n0x0100 - 0x024F: \nLatin Extended A/B blocks, mostly in \"AllegroOpen\" font:");
            break;
        case 0x0250:
            builder.Writeln("\n\n0x0250 - 0x052F: \nIPA/Greek/Cyrillic blocks in \"M+ 2m\" font:");
            break;
    }

    builder.Write($"{Convert.ToChar(i)}");
}

doc.Save(ArtifactsDir + "FontSettings.FallbackSettingsCustom.pdf");
```

### Se även

* class [FontFallbackSettings](../)
* namnutrymme [Aspose.Words.Fonts](../../fontfallbacksettings/)
* hopsättning [Aspose.Words](../../../)


