---
title: Font.ClearFormatting
second_title: Aspose.Words för .NET API Referens
description: Font metod. Återställer till standardtypsnittsformatering.
type: docs
weight: 550
url: /sv/net/aspose.words/font/clearformatting/
---
## Font.ClearFormatting method

Återställer till standardtypsnittsformatering.

```csharp
public void ClearFormatting()
```

### Anmärkningar

Tar bort all typsnittsformatering som uttryckligen anges på objektet från which  **Font** erhölls så att teckensnittsformateringen kommer att ärvas från lämplig förälder.

### Exempel

Visar hur man infogar ett hyperlänkfält.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("For more information, please visit the ");

// Infoga en hyperlänk och framhäva den med anpassad formatering.
// Hyperlänken kommer att vara ett klickbart stycke text som tar oss till den plats som anges i URL:en.
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;
builder.InsertHyperlink("Google website", "https://www.google.com", false);
builder.Font.ClearFormatting();
builder.Writeln(".");

// Ctrl + vänsterklicka på länken i texten i Microsoft Word tar oss till URL:en via ett nytt webbläsarfönster.
doc.Save(ArtifactsDir + "DocumentBuilder.InsertHyperlink.docx");
```

### Se även

* class [Font](../)
* namnutrymme [Aspose.Words](../../font/)
* hopsättning [Aspose.Words](../../../)


