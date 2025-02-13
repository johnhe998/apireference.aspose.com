---
title: HtmlSaveOptions.ExportDropDownFormFieldAsText
second_title: Aspose.Words för .NET API Referens
description: HtmlSaveOptions fast egendom. Styr hur formulärfält i rullgardinsmenyn sparas i HTML eller MHTML. Standardvärdet ärfalsk .
type: docs
weight: 140
url: /sv/net/aspose.words.saving/htmlsaveoptions/exportdropdownformfieldastext/
---
## HtmlSaveOptions.ExportDropDownFormFieldAsText property

Styr hur formulärfält i rullgardinsmenyn sparas i HTML eller MHTML. Standardvärdet är`falsk` .

```csharp
public bool ExportDropDownFormFieldAsText { get; set; }
```

### Anmärkningar

När inställd på`Sann` , exporterar rullgardinsfält som normal text. When`falsk`, exporterar rullgardinsfält som SELECT-element i HTML.

Vid export till EPUB sparas formulärfälten i rullgardinsmenyn alltid som text på grund av till kraven i detta format.

### Exempel

Visar hur du får formulärfält i rullgardinsmenyn att smälta in med stycketext när du sparar till html.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Använd en dokumentbyggare för att infoga en kombinationsruta med värdet "Två" markerat.
builder.InsertComboBox("MyComboBox", new[] { "One", "Two", "Three" }, 1);

// Flaggan "ExportDropDownFormFieldAsText" för detta SaveOptions-objekt tillåter oss att
// styr hur du hanterar kombinationsrutor när du sparar dokumentet i HTML.
// Om du ställer in den på "true" konverteras varje kombinationsruta till enkel text
// som visar kombinationsrutans för närvarande valda värde, vilket effektivt fryser det.
// Om du ställer in den på "false" bevaras kombinationsrutans funktionalitet med <select> och <alternativ> taggar.
HtmlSaveOptions options = new HtmlSaveOptions();
options.ExportDropDownFormFieldAsText = exportDropDownFormFieldAsText;    

doc.Save(ArtifactsDir + "HtmlSaveOptions.DropDownFormField.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.DropDownFormField.html");

if (exportDropDownFormFieldAsText)
    Assert.True(outDocContents.Contains(
        "<span>Two</span>"));
else
    Assert.True(outDocContents.Contains(
        "<select name=\"MyComboBox\">" +
            "<option>One</option>" +
            "<option selected=\"selected\">Two</option>" +
            "<option>Three</option>" +
        "</select>"));
```

### Se även

* class [HtmlSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../htmlsaveoptions/)
* hopsättning [Aspose.Words](../../../)


