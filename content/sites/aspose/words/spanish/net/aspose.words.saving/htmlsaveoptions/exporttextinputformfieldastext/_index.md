---
title: HtmlSaveOptions.ExportTextInputFormFieldAsText
second_title: Referencia de API de Aspose.Words para .NET
description: HtmlSaveOptions propiedad. Controla cómo se guardan los campos de formulario de entrada de texto en HTML o MHTML. El valor predeterminado esfalso .
type: docs
weight: 270
url: /es/net/aspose.words.saving/htmlsaveoptions/exporttextinputformfieldastext/
---
## HtmlSaveOptions.ExportTextInputFormFieldAsText property

Controla cómo se guardan los campos de formulario de entrada de texto en HTML o MHTML. El valor predeterminado es`falso` .

```csharp
public bool ExportTextInputFormFieldAsText { get; set; }
```

### Observaciones

cuando se establece en`verdadero` , exporta campos de formulario de entrada de texto como texto normal. cuando`falso`, exporta campos de formulario de entrada de texto de Word como elementos INPUT en HTML.

Al exportar a EPUB, los campos del formulario de entrada de texto siempre se guardan como texto debido a los requisitos de este formato.

### Ejemplos

Muestra cómo especificar la carpeta para almacenar imágenes vinculadas después de guardarlas en .html.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

string imagesDir = Path.Combine(ArtifactsDir, "SaveHtmlWithOptions");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

// Establecer una opción para exportar campos de formulario como texto sin formato en lugar de elementos de entrada HTML.
HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true, 
    ImagesFolder = imagesDir
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveHtmlWithOptions.html", options);
```

### Ver también

* class [HtmlSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../htmlsaveoptions/)
* asamblea [Aspose.Words](../../../)


