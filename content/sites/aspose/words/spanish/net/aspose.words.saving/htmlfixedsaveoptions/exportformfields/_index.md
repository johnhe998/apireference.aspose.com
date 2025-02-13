---
title: HtmlFixedSaveOptions.ExportFormFields
second_title: Referencia de API de Aspose.Words para .NET
description: HtmlFixedSaveOptions propiedad. Obtiene o establece la indicación de si los campos de formulario se exportan como elementos interactivos como etiqueta de entrada en lugar de convertirlos en texto o gráficos.
type: docs
weight: 80
url: /es/net/aspose.words.saving/htmlfixedsaveoptions/exportformfields/
---
## HtmlFixedSaveOptions.ExportFormFields property

Obtiene o establece la indicación de si los campos de formulario se exportan como elementos interactivos (como etiqueta de "entrada") en lugar de convertirlos en texto o gráficos.

```csharp
public bool ExportFormFields { get; set; }
```

### Ejemplos

Muestra cómo exportar campos de formulario a Html.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertCheckBox("CheckBox", false, 15);

// Cuando exportamos un documento con campos de formulario a .html,
// hay dos formas en que Aspose.Words puede exportar campos de formulario.
// Establecer el indicador "ExportFormFields" en "true" los exportará como objetos interactivos.
// Establecer este indicador en "falso" mostrará los campos de formulario como texto sin formato.
// Esto los congelará en su valor actual y evitará que el lector de nuestro documento HTML
// de poder interactuar con ellos.
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    ExportFormFields = exportFormFields
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.ExportFormFields.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.ExportFormFields.html");

if (exportFormFields)
{
    Assert.True(Regex.Match(outDocContents,
        "<a name=\"CheckBox\" style=\"left:0pt; top:0pt;\"></a>" +
        "<input style=\"position:absolute; left:0pt; top:0pt;\" type=\"checkbox\" name=\"CheckBox\" />").Success);
}
else
{
    Assert.True(Regex.Match(outDocContents, 
        "<a name=\"CheckBox\" style=\"left:0pt; top:0pt;\"></a>" +
        "<div class=\"awdiv\" style=\"left:0.8pt; top:0.8pt; width:14.25pt; height:14.25pt; border:solid 0.75pt #000000;\"").Success);
}
```

### Ver también

* class [HtmlFixedSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* asamblea [Aspose.Words](../../../)


