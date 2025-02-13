---
title: HtmlSaveOptions.ExportHeadersFootersMode
second_title: Referencia de API de Aspose.Words para .NET
description: HtmlSaveOptions propiedad. Especifica cómo se envían los encabezados y pies de página a HTML MHTML o EPUB. El valor predeterminado esPerSection para HTML/MHTML yNone para EPUB.
type: docs
weight: 170
url: /es/net/aspose.words.saving/htmlsaveoptions/exportheadersfootersmode/
---
## HtmlSaveOptions.ExportHeadersFootersMode property

Especifica cómo se envían los encabezados y pies de página a HTML, MHTML o EPUB. El valor predeterminado esPerSection para HTML/MHTML yNone para EPUB.

```csharp
public ExportHeadersFootersMode ExportHeadersFootersMode { get; set; }
```

### Observaciones

Es difícil enviar encabezados y pies de página de manera significativa a HTML porque HTML no está paginado.

Cuando esta propiedad esPerSection, Aspose.Words exporta solo encabezados y pies de página principales al principio y al final de cada sección.

cuando esFirstSectionHeaderLastSectionFooter solo se exportan el primer encabezado principal y el último pie de página principal (incluido el vinculado al anterior).

Puede deshabilitar la exportación de encabezados y pies de página por completo configurando esta propiedad enNone.

### Ejemplos

Muestra cómo omitir encabezados/pies de página al guardar un documento en HTML.

```csharp
Document doc = new Document(MyDir + "Header and footer types.docx");

// Este documento contiene encabezados y pies de página. Podemos acceder a ellos a través de la colección "HeadersFooters".
Assert.AreEqual("First header", doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderFirst].GetText().Trim());

// Los formatos como .html no dividen el documento en páginas, por lo que los encabezados/pies de página no funcionarán de la misma manera
// lo harían cuando abrimos el documento como .docx usando Microsoft Word.
// Si convertimos un documento con encabezados/pies de página a html, la conversión asimilará los encabezados/pies de página en el cuerpo del texto.
// Podemos usar un objeto SaveOptions para omitir encabezados/pies de página al convertir a html.
HtmlSaveOptions saveOptions =
    new HtmlSaveOptions(SaveFormat.Html) { ExportHeadersFootersMode = ExportHeadersFootersMode.None };

doc.Save(ArtifactsDir + "HeaderFooter.ExportMode.html", saveOptions);

// Abrimos nuestro documento guardado y verificamos que no contenga el texto del encabezado
doc = new Document(ArtifactsDir + "HeaderFooter.ExportMode.html");

Assert.IsFalse(doc.Range.Text.Contains("First header"));
```

### Ver también

* enum [ExportHeadersFootersMode](../../exportheadersfootersmode/)
* class [HtmlSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../htmlsaveoptions/)
* asamblea [Aspose.Words](../../../)


