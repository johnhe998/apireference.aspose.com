---
title: HtmlLoadOptions.SupportVml
second_title: Aspose.Words för .NET API Referens
description: HtmlLoadOptions fast egendom. Hämtar eller ställer in ett värde som anger om VMLbilder ska stödjas.
type: docs
weight: 60
url: /sv/net/aspose.words.loading/htmlloadoptions/supportvml/
---
## HtmlLoadOptions.SupportVml property

Hämtar eller ställer in ett värde som anger om VML-bilder ska stödjas.

```csharp
public bool SupportVml { get; set; }
```

### Exempel

Visar hur man stödjer villkorliga kommentarer när ett HTML-dokument laddas.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions();

// Om värdet är sant tar vi hänsyn till VML-koden när vi analyserar det laddade dokumentet.
loadOptions.SupportVml = supportVml;

// Detta dokument innehåller en JPEG-bild inom "<!--[if gte vml 1]>" taggar,
// och en annan PNG-bild inom "<![if !vml]>" taggar.
// Om vi ställer in "SupportVml"-flaggan till "true", kommer Aspose.Words att ladda JPEG.
// Om vi sätter denna flagga till "false", så kommer Aspose.Words bara att ladda PNG.
Document doc = new Document(MyDir + "VML conditional.htm", loadOptions);

if (supportVml)
    Assert.AreEqual(ImageType.Jpeg, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
else
    Assert.AreEqual(ImageType.Png, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
```

### Se även

* class [HtmlLoadOptions](../)
* namnutrymme [Aspose.Words.Loading](../../htmlloadoptions/)
* hopsättning [Aspose.Words](../../../)


