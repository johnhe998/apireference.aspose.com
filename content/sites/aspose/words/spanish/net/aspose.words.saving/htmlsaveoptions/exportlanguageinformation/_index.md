---
title: HtmlSaveOptions.ExportLanguageInformation
second_title: Referencia de API de Aspose.Words para .NET
description: HtmlSaveOptions propiedad. Especifica si la información de idioma se exporta a HTML MHTML o EPUB. El valor predeterminado esfalso .
type: docs
weight: 190
url: /es/net/aspose.words.saving/htmlsaveoptions/exportlanguageinformation/
---
## HtmlSaveOptions.ExportLanguageInformation property

Especifica si la información de idioma se exporta a HTML, MHTML o EPUB. El valor predeterminado es`falso` .

```csharp
public bool ExportLanguageInformation { get; set; }
```

### Observaciones

Cuando esta propiedad se establece en`verdadero` Salidas de Aspose.Words **idioma** Atributo HTML en los elementos document que especifican el idioma. Esto puede ser necesario para preservar la semántica relacionada con el lenguaje.

### Ejemplos

Muestra cómo conservar la información del idioma al guardar en .html.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Use el constructor para escribir texto mientras lo formatea en diferentes configuraciones regionales.
builder.Font.LocaleId = new CultureInfo("en-US").LCID;
builder.Writeln("Hello world!");

builder.Font.LocaleId = new CultureInfo("en-GB").LCID;
builder.Writeln("Hello again!");

builder.Font.LocaleId = new CultureInfo("ru-RU").LCID;
builder.Write("Привет, мир!");

// Al guardar el documento en HTML, podemos pasar un objeto SaveOptions
// para conservar o descartar la configuración regional de cada texto formateado.
// Si establecemos el indicador "ExportLanguageInformation" en "true",
// el documento HTML de salida contendrá las configuraciones regionales en los atributos "lang" de <span> etiquetas
// Si establecemos el indicador "ExportLanguageInformation" en "falso",
// el texto en el documento HTML de salida no contendrá ninguna información de configuración regional.
HtmlSaveOptions options = new HtmlSaveOptions
{
    ExportLanguageInformation = exportLanguageInformation,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportLanguageInformation.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportLanguageInformation.html");

if (exportLanguageInformation)
{
    Assert.True(outDocContents.Contains("<span>Hello world!</span>"));
    Assert.True(outDocContents.Contains("<span lang=\"en-GB\">Hello again!</span>"));
    Assert.True(outDocContents.Contains("<span lang=\"ru-RU\">Привет, мир!</span>"));
}
else
{
    Assert.True(outDocContents.Contains("<span>Hello world!</span>"));
    Assert.True(outDocContents.Contains("<span>Hello again!</span>"));
    Assert.True(outDocContents.Contains("<span>Привет, мир!</span>"));
}
```

### Ver también

* class [HtmlSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../htmlsaveoptions/)
* asamblea [Aspose.Words](../../../)


