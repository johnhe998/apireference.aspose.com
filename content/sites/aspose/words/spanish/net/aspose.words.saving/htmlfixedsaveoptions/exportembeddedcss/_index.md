---
title: HtmlFixedSaveOptions.ExportEmbeddedCss
second_title: Referencia de API de Aspose.Words para .NET
description: HtmlFixedSaveOptions propiedad. Especifica si el CSS hoja de estilo en cascada se debe incrustar en el documento HTML.
type: docs
weight: 40
url: /es/net/aspose.words.saving/htmlfixedsaveoptions/exportembeddedcss/
---
## HtmlFixedSaveOptions.ExportEmbeddedCss property

Especifica si el CSS (hoja de estilo en cascada) se debe incrustar en el documento HTML.

```csharp
public bool ExportEmbeddedCss { get; set; }
```

### Ejemplos

Muestra cómo determinar dónde almacenar las hojas de estilo CSS al exportar un documento a Html.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Cuando exportamos un documento a html, Aspose.Words también creará una hoja de estilo CSS para formatear el documento.
// Estableciendo el indicador "ExportEmbeddedCss" en "verdadero", guarde la hoja de estilo CSS en un archivo .css,
// y enlace al archivo desde el documento html usando un <enlace> elemento.
// Establecer el indicador en "falso" incrustará la hoja de estilo CSS dentro del documento Html,
// que creará solo un archivo en lugar de dos.
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    ExportEmbeddedCss = exportEmbeddedCss
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss.html");

if (exportEmbeddedCss)
{
    Assert.True(Regex.Match(outDocContents, "<style type=\"text/css\">").Success);
    Assert.False(File.Exists(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss/styles.css"));
}
else
{
    Assert.True(Regex.Match(outDocContents,
        "<link rel=\"stylesheet\" type=\"text/css\" href=\"HtmlFixedSaveOptions[.]ExportEmbeddedCss/styles[.]css\" media=\"all\" />").Success);
    Assert.True(File.Exists(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss/styles.css"));
}
```

### Ver también

* class [HtmlFixedSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* asamblea [Aspose.Words](../../../)


