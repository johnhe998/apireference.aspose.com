---
title: HtmlSaveOptions.ImagesFolder
second_title: Referencia de API de Aspose.Words para .NET
description: HtmlSaveOptions propiedad. Especifica la carpeta física donde se guardan las imágenes al exportar un documento a formato HTML. El valor predeterminado es una cadena vacía.
type: docs
weight: 370
url: /es/net/aspose.words.saving/htmlsaveoptions/imagesfolder/
---
## HtmlSaveOptions.ImagesFolder property

Especifica la carpeta física donde se guardan las imágenes al exportar un documento a formato HTML. El valor predeterminado es una cadena vacía.

```csharp
public string ImagesFolder { get; set; }
```

### Observaciones

Cuando guardas un[`Document`](../../../aspose.words/document/) en formato HTML, Aspose.Words necesita guardar todas las imágenes incrustadas en el documento como archivos independientes.`ImagesFolder` le permite especificar dónde se guardarán las imágenes y[`ImagesFolderAlias`](../imagesfolderalias/) permite especificar cómo se construirán las URI de la imagen.

Si guarda un documento en un archivo y proporciona un nombre de archivo, Aspose.Words, de forma predeterminada, guarda las imágenes en la misma carpeta donde se guarda el archivo del documento. Usar`ImagesFolder` para anular este comportamiento.

Si guarda un documento en una secuencia, Aspose.Words no tiene una carpeta donde guardar las imágenes, pero aún necesita guardar las imágenes en algún lugar. En este caso, debe especificar una carpeta accesible en el`ImagesFolder` propiedad o proporcionar secuencias personalizadas a través de el[`ImageSavingCallback`](../imagesavingcallback/) controlador de eventos.

Si la carpeta especificada por`ImagesFolder` no existe, se creará automáticamente.

[`ResourceFolder`](../resourcefolder/) es otra forma de especificar una carpeta donde se deben guardar las imágenes.

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


