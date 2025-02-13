---
title: Enum ExportFontFormat
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Saving.ExportFontFormat uppräkning. Indikerar formatet som används för att exportera teckensnitt vid rendering till HTMLfast format.
type: docs
weight: 4730
url: /sv/net/aspose.words.saving/exportfontformat/
---
## ExportFontFormat enumeration

Indikerar formatet som används för att exportera teckensnitt vid rendering till HTML-fast format.

```csharp
public enum ExportFontFormat
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Woff | `0` | WOFF (Web Open Font Format). |
| Ttf | `1` | TTF (TrueType Font-format). |

### Exempel

Visar hur teckensnitt endast används från målmaskinen när du sparar ett dokument i HTML.

```csharp
Document doc = new Document(MyDir + "Bullet points with alternative font.docx");

HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions
{
    ExportEmbeddedCss = true,
    UseTargetMachineFonts = useTargetMachineFonts,
    FontFormat = ExportFontFormat.Ttf,
    ExportEmbeddedFonts = false,
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.UsingMachineFonts.html", saveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.UsingMachineFonts.html");

if (useTargetMachineFonts)
    Assert.False(Regex.Match(outDocContents, "@font-face").Success);
else
    Assert.True(Regex.Match(outDocContents,
        "@font-face { font-family:'Arial'; font-style:normal; font-weight:normal; src:local[(]'☺'[)], " +
        "url[(]'HtmlFixedSaveOptions.UsingMachineFonts/font001.ttf'[)] format[(]'truetype'[)]; }").Success);
```

### Se även

* property [FontFormat](../htmlfixedsaveoptions/fontformat/)
* namnutrymme [Aspose.Words.Saving](../../aspose.words.saving/)
* hopsättning [Aspose.Words](../../)


