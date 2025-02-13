---
title: HtmlSaveOptions.ExportDropDownFormFieldAsText
second_title: Referencia de API de Aspose.Words para .NET
description: HtmlSaveOptions propiedad. Controla cómo se guardan los campos del formulario desplegable en HTML o MHTML. El valor predeterminado esfalso .
type: docs
weight: 140
url: /es/net/aspose.words.saving/htmlsaveoptions/exportdropdownformfieldastext/
---
## HtmlSaveOptions.ExportDropDownFormFieldAsText property

Controla cómo se guardan los campos del formulario desplegable en HTML o MHTML. El valor predeterminado es`falso` .

```csharp
public bool ExportDropDownFormFieldAsText { get; set; }
```

### Observaciones

cuando se establece en`verdadero` , exporta campos de formulario desplegables como texto normal. Cuando`falso`, exporta campos de formulario desplegables como elemento SELECT en HTML.

Al exportar a EPUB, los campos de formulario desplegables de texto siempre se guardan como texto debido a los requisitos de este formato .

### Ejemplos

Muestra cómo obtener campos de formulario de cuadro combinado desplegable para combinar con el texto del párrafo al guardar en html.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Use un generador de documentos para insertar un cuadro combinado con el valor "Dos" seleccionado.
builder.InsertComboBox("MyComboBox", new[] { "One", "Two", "Three" }, 1);

// El indicador "ExportDropDownFormFieldAsText" de este objeto SaveOptions nos permite
// controla cómo guardar el documento en HTML trata los cuadros combinados desplegables.
// Establecerlo en "verdadero" convertirá cada cuadro combinado en texto simple
// que muestra el valor seleccionado actualmente del cuadro combinado, congelándolo efectivamente.
// Establecerlo en "false" preservará la funcionalidad del cuadro combinado usando <select> y <opción> etiquetas
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

### Ver también

* class [HtmlSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../htmlsaveoptions/)
* asamblea [Aspose.Words](../../../)


