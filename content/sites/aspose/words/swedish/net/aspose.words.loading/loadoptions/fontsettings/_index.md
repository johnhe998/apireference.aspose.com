---
title: LoadOptions.FontSettings
second_title: Aspose.Words för .NET API Referens
description: LoadOptions fast egendom. Gör det möjligt att ange inställningar för dokumentteckensnitt.
type: docs
weight: 70
url: /sv/net/aspose.words.loading/loadoptions/fontsettings/
---
## LoadOptions.FontSettings property

Gör det möjligt att ange inställningar för dokumentteckensnitt.

```csharp
public FontSettings FontSettings { get; set; }
```

### Anmärkningar

När du laddar vissa format kan Aspose.Words behöva lösa teckensnitten. Till exempel, när du laddar HTML-dokument kan Aspose.Words lösa teckensnitten för att utföra fallback.

Om inställt på null, standardinställning för statiska teckensnitt[`DefaultInstance`](../../../aspose.words.fonts/fontsettings/defaultinstance/) kommer att användas.

Standardvärdet är null.

### Exempel

Visar hur du tillämpar inställningar för teckensnittsersättning när du laddar ett dokument.

```csharp
// Skapa ett FontSettings-objekt som kommer att ersätta typsnittet "Times New Roman".
// med typsnittet "Arvo" från vår "MyFonts"-mapp.
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(FontsDir, false);
fontSettings.SubstitutionSettings.TableSubstitution.AddSubstitutes("Times New Roman", "Arvo");

// Ställ in det FontSettings-objektet som en egenskap för ett nyskapat LoadOptions-objekt.
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;

// Ladda dokumentet och rendera det sedan som en PDF med teckensnittsersättningen.
Document doc = new Document(MyDir + "Document.docx", loadOptions);

doc.Save(ArtifactsDir + "LoadOptions.FontSettings.pdf");
```

Visar hur man anger teckensnittsersättningar under laddning.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = new FontSettings();

// Ställ in en teckensnittsersättningsregel för ett LoadOptions-objekt.
// Om dokumentet vi laddar använder ett teckensnitt som vi inte har,
// denna regel kommer att ersätta det otillgängliga teckensnittet med ett som finns.
// I det här fallet kommer all användning av "MissingFont" att konverteras till "Comic Sans MS".
TableSubstitutionRule substitutionRule = loadOptions.FontSettings.SubstitutionSettings.TableSubstitution;
substitutionRule.AddSubstitutes("MissingFont", new[] {"Comic Sans MS"});

Document doc = new Document(MyDir + "Missing font.html", loadOptions);

// Vid det här laget kommer sådan text fortfarande att finnas i "MissingFont".
// Teckensnittsbyte kommer att ske när vi renderar dokumentet.
Assert.AreEqual("MissingFont", doc.FirstSection.Body.FirstParagraph.Runs[0].Font.Name);

doc.Save(ArtifactsDir + "FontSettings.ResolveFontsBeforeLoadingDocument.pdf");
```

### Se även

* class [FontSettings](../../../aspose.words.fonts/fontsettings/)
* class [LoadOptions](../)
* namnutrymme [Aspose.Words.Loading](../../loadoptions/)
* hopsättning [Aspose.Words](../../../)


