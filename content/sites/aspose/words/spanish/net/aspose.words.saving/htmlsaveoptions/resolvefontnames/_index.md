---
title: HtmlSaveOptions.ResolveFontNames
second_title: Referencia de API de Aspose.Words para .NET
description: HtmlSaveOptions propiedad. Especifica si los nombres de familia de fuentes utilizados en el documento se resuelven y sustituyen de acuerdo con FontSettings cuando se escribe en formatos basados en HTML.
type: docs
weight: 410
url: /es/net/aspose.words.saving/htmlsaveoptions/resolvefontnames/
---
## HtmlSaveOptions.ResolveFontNames property

Especifica si los nombres de familia de fuentes utilizados en el documento se resuelven y sustituyen de acuerdo con [`FontSettings`](../../../aspose.words/document/fontsettings/) cuando se escribe en formatos basados en HTML.

```csharp
public bool ResolveFontNames { get; set; }
```

### Observaciones

De forma predeterminada, esta opción está establecida en`falso` los nombres de las familias de fuentes se escriben en HTML como se especifica en los documentos de origen. Eso es,[`FontSettings`](../../../aspose.words/document/fontsettings/) se ignoran y no se realiza ninguna resolución o sustitución de nombres de familias de fuentes.

Si esta opción se establece en`verdadero` , Aspose.Words utiliza[`FontSettings`](../../../aspose.words/document/fontsettings/) para resolver cada nombre de familia de fuentes especificado en un documento de origen en el nombre de una familia de fuentes disponible, realizando la sustitución de fuentes según sea necesario.

### Ejemplos

Muestra cómo resolver todos los nombres de fuentes antes de escribirlos en HTML.

```csharp
Document doc = new Document(MyDir + "Missing font.docx");

// Este documento contiene texto que nombra una fuente que no tenemos.
Assert.NotNull(doc.FontInfos["28 Days Later"]);

// Si no tenemos forma de obtener esta fuente y queremos poder mostrar todo el texto
// en este documento en un HTML de salida, podemos sustituirlo por otra fuente.
FontSettings fontSettings = new FontSettings
{
    SubstitutionSettings =
    {
        DefaultFontSubstitution =
        {
            DefaultFontName = "Arial",
            Enabled = true
        }
    }
};

doc.FontSettings = fontSettings;

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
    // De forma predeterminada, esta opción se establece en 'False' y Aspose.Words escribe los nombres de fuentes como se especifica en el documento de origen
    ResolveFontNames = resolveFontNames
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ResolveFontNames.html", saveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ResolveFontNames.html");

Assert.True(resolveFontNames
    ? Regex.Match(outDocContents, "<span style=\"font-family:Arial\">").Success
    : Regex.Match(outDocContents, "<span style=\"font-family:\'28 Days Later\'\">").Success);
```

### Ver también

* class [HtmlSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../htmlsaveoptions/)
* asamblea [Aspose.Words](../../../)


