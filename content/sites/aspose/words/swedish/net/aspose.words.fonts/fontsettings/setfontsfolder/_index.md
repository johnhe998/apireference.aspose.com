---
title: FontSettings.SetFontsFolder
second_title: Aspose.Words för .NET API Referens
description: FontSettings metod. Ställer in mappen där Aspose.Words söker efter TrueTypeteckensnitt vid rendering av dokument eller inbäddning av teckensnitt. Detta är en genväg tillSetFontsFolders för att endast ställa in en teckensnittskatalog.
type: docs
weight: 80
url: /sv/net/aspose.words.fonts/fontsettings/setfontsfolder/
---
## FontSettings.SetFontsFolder method

Ställer in mappen där Aspose.Words söker efter TrueType-teckensnitt vid rendering av dokument eller inbäddning av teckensnitt. Detta är en genväg till[`SetFontsFolders`](../setfontsfolders/) för att endast ställa in en teckensnittskatalog.

```csharp
public void SetFontsFolder(string fontFolder, bool recursive)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| fontFolder | String | Mappen som innehåller TrueType-teckensnitt. |
| recursive | Boolean | True för att skanna de angivna mapparna efter teckensnitt rekursivt. |

### Exempel

Visar hur man ställer in en teckensnittskällkatalog.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arvo";
builder.Writeln("Hello world!");
builder.Font.Name = "Amethysta";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Våra teckensnittskällor innehåller inte det teckensnitt som vi har använt för text i detta dokument.
// Om vi använder dessa teckensnittsinställningar när vi renderar detta dokument,
// Aspose.Words kommer att tillämpa ett reservteckensnitt på text som har ett teckensnitt som Aspose.Words inte kan hitta.
FontSourceBase[] originalFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.AreEqual(1, originalFontSources.Length);
Assert.True(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));

// Standardteckensnittskällorna saknar de två typsnitten som vi använder i det här dokumentet.
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));

// Använd metoden "SetFontsFolder" för att ställa in en katalog som kommer att fungera som en ny teckensnittskälla.
// Skicka "false" som det "rekursiva" argumentet för att inkludera teckensnitt från alla teckensnittsfiler som finns i katalogen
// som vi skickar i det första argumentet, men inte inkluderar några teckensnitt i någon av den katalogens undermappar.
// Skicka "true" som det "rekursiva" argumentet för att inkludera alla teckensnittsfiler i katalogen som vi skickar
// i det första argumentet, såväl som alla teckensnitt i dess underkataloger.
FontSettings.DefaultInstance.SetFontsFolder(FontsDir, recursive);

FontSourceBase[] newFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.AreEqual(1, newFontSources.Length);
Assert.False(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.True(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

// Teckensnittet "Amethysta" finns i en undermapp till teckensnittskatalogen.
if (recursive)
{
    Assert.AreEqual(25, newFontSources[0].GetAvailableFonts().Count);
    Assert.True(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
}
else
{
    Assert.AreEqual(18, newFontSources[0].GetAvailableFonts().Count);
    Assert.False(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
}

doc.Save(ArtifactsDir + "FontSettings.SetFontsFolder.pdf");

// Återställ de ursprungliga teckensnittskällorna.
FontSettings.DefaultInstance.SetFontsSources(originalFontSources);
```

### Se även

* class [FontSettings](../)
* namnutrymme [Aspose.Words.Fonts](../../fontsettings/)
* hopsättning [Aspose.Words](../../../)


