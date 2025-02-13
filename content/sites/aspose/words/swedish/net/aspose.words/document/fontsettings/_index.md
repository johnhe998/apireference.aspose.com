---
title: Document.FontSettings
second_title: Aspose.Words för .NET API Referens
description: Document fast egendom. Hämtar eller ställer in dokumentfontinställningar.
type: docs
weight: 140
url: /sv/net/aspose.words/document/fontsettings/
---
## Document.FontSettings property

Hämtar eller ställer in dokumentfontinställningar.

```csharp
public FontSettings FontSettings { get; set; }
```

### Anmärkningar

Den här egenskapen gör det möjligt att ange teckensnittsinställningar per dokument. Om inställt på null, standard statiska teckensnitt settings [`DefaultInstance`](../../../aspose.words.fonts/fontsettings/defaultinstance/) kommer att användas.

Standardvärdet är null.

### Exempel

Visar hur du ställer in regler för teckensnittsersättning.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Amethysta";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

FontSourceBase[] fontSources = FontSettings.DefaultInstance.GetFontsSources();

// Standardteckensnittskällorna innehåller det första teckensnittet som dokumentet använder.
Assert.AreEqual(1, fontSources.Length);
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));

// Det andra teckensnittet, "Amethysta", är inte tillgängligt.
Assert.False(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));

// Vi kan konfigurera en teckensnittsersättningstabell som avgör
// vilka typsnitt Aspose.Words kommer att använda som ersättning för otillgängliga teckensnitt.
// Ställ in två ersättningsteckensnitt för "Amethysta": "Arvo" och "Courier New".
// Om den första ersättningen inte är tillgänglig försöker Aspose.Words använda den andra ersättningen och så vidare.
doc.FontSettings = new FontSettings();
doc.FontSettings.SubstitutionSettings.TableSubstitution.SetSubstitutes(
    "Amethysta", new[] {"Arvo", "Courier New"});

  // "Amethysta" är inte tillgängligt, och substitutionsregeln säger att det första teckensnittet som används som ersättning är "Arvo".
Assert.False(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

  // "Arvo" är inte heller tillgänglig, men "Courier New" är det.
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Courier New"));

// Utdatadokumentet kommer att visa texten som använder "Amethysta"-teckensnittet formaterat med "Courier New".
doc.Save(ArtifactsDir + "FontSettings.TableSubstitution.pdf");
```

### Se även

* class [FontSettings](../../../aspose.words.fonts/fontsettings/)
* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)


