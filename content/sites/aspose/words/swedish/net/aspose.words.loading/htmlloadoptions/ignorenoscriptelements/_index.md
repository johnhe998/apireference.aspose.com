---
title: HtmlLoadOptions.IgnoreNoscriptElements
second_title: Aspose.Words för .NET API Referens
description: HtmlLoadOptions fast egendom. Hämtar eller ställer in ett värde som anger om noscript HTMLelement ska ignoreras. Standardvärdet ärfalsk .
type: docs
weight: 40
url: /sv/net/aspose.words.loading/htmlloadoptions/ignorenoscriptelements/
---
## HtmlLoadOptions.IgnoreNoscriptElements property

Hämtar eller ställer in ett värde som anger om &lt;noscript&gt; HTML-element ska ignoreras. Standardvärdet är`falsk` .

```csharp
public bool IgnoreNoscriptElements { get; set; }
```

### Anmärkningar

Liksom MS Word stöder inte Aspose.Words skript och laddar som standard innehåll av &lt;noscript&gt; elements till det resulterande dokumentet. I de flesta webbläsare stöds dock skript och innehåll från &lt;noscript&gt; är inte synligt. Ställer in den här egenskapen till`Sann` tvingar Aspose.Words att ignorera alla &lt;noscript&gt;-element och hjälper till att skapa dokument som ser närmare det som visas i webbläsare.

### Exempel

Visar hur man ignorerar &lt;noscript&gt; HTML-element.

```csharp
const string html = @"
    <html>
      <head>
        <title>NOSCRIPT</title>
          <meta http-equiv=""Content-Type"" content=""text/html; charset=utf-8"">
          <script type=""text/javascript"">
            alert(""Hello, world!"");
          </script>
      </head>
    <body>
      <noscript><p>Your browser does not support JavaScript!</p></noscript>
    </body>
    </html>";

HtmlLoadOptions htmlLoadOptions = new HtmlLoadOptions();
htmlLoadOptions.IgnoreNoscriptElements = ignoreNoscriptElements;

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), htmlLoadOptions);
doc.Save(ArtifactsDir + "HtmlLoadOptions.IgnoreNoscriptElements.pdf");
```

### Se även

* class [HtmlLoadOptions](../)
* namnutrymme [Aspose.Words.Loading](../../htmlloadoptions/)
* hopsättning [Aspose.Words](../../../)


