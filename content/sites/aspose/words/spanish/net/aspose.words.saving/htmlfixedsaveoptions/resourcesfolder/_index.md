---
title: HtmlFixedSaveOptions.ResourcesFolder
second_title: Referencia de API de Aspose.Words para .NET
description: HtmlFixedSaveOptions propiedad. Especifica la carpeta física donde se guardan los recursos imágenes fuentes css al exportar un documento a formato Html. El valor predeterminado esnulo .
type: docs
weight: 140
url: /es/net/aspose.words.saving/htmlfixedsaveoptions/resourcesfolder/
---
## HtmlFixedSaveOptions.ResourcesFolder property

Especifica la carpeta física donde se guardan los recursos (imágenes, fuentes, css) al exportar un documento a formato Html. El valor predeterminado es`nulo` .

```csharp
public string ResourcesFolder { get; set; }
```

### Observaciones

Sólo tiene efecto si[`ExportEmbeddedImages`](../exportembeddedimages/) propiedad es falsa.

Cuando guardas un[`Document`](../../../aspose.words/document/) en formato HTML, Aspose.Words necesita guardar todas las imágenes x000d_ incrustadas en el documento como archivos independientes.`ResourcesFolder` le permite especificar dónde se guardarán las imágenes y[`ResourcesFolderAlias`](../resourcesfolderalias/) permite especificar cómo se construirán las URI de la imagen.

Si guarda un documento en un archivo y proporciona un nombre de archivo, Aspose.Words, de forma predeterminada, guarda las imágenes en la misma carpeta donde se guarda el archivo del documento. Usar`ResourcesFolder` para anular este comportamiento.

Si guarda un documento en una transmisión, Aspose.Words no tiene una carpeta donde guardar las imágenes, pero aún necesita guardar las imágenes en algún lugar. En este caso, debe especificar una carpeta accesible utilizando el`ResourcesFolder` propiedad

### Ejemplos

Muestra cómo usar una devolución de llamada para imprimir los URI de los recursos externos creados al convertir un documento a HTML.

```csharp
public void HtmlFixedResourceFolder()
{
    Document doc = new Document(MyDir + "Rendering.docx");

    ResourceUriPrinter callback = new ResourceUriPrinter();

    HtmlFixedSaveOptions options = new HtmlFixedSaveOptions
    {
        SaveFormat = SaveFormat.HtmlFixed,
        ExportEmbeddedImages = false,
        ResourcesFolder = ArtifactsDir + "HtmlFixedResourceFolder",
        ResourcesFolderAlias = ArtifactsDir + "HtmlFixedResourceFolderAlias",
        ShowPageBorder = false,
        ResourceSavingCallback = callback
    };

    // Una carpeta especificada por ResourcesFolderAlias contendrá los recursos en lugar de ResourcesFolder.
    // Debemos asegurarnos de que la carpeta exista antes de que los flujos puedan poner sus recursos en ella.
    Directory.CreateDirectory(options.ResourcesFolderAlias);

    doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.HtmlFixedResourceFolder.html", options);

    Console.WriteLine(callback.GetText());

    string[] resourceFiles = Directory.GetFiles(ArtifactsDir + "HtmlFixedResourceFolderAlias");

    Assert.False(Directory.Exists(ArtifactsDir + "HtmlFixedResourceFolder"));
    Assert.AreEqual(6, resourceFiles.Count(f => f.EndsWith(".jpeg") || f.EndsWith(".png") || f.EndsWith(".css")));
}

/// <summary>
/// Cuenta e imprime los URI de los recursos contenidos en cuando se convierten a HTML fijo.
/// </summary>
private class ResourceUriPrinter : IResourceSavingCallback
{
    void IResourceSavingCallback.ResourceSaving(ResourceSavingArgs args)
    {
        // Si establecemos un alias de carpeta en el objeto SaveOptions, podremos imprimirlo desde aquí.
        mText.AppendLine($"Resource #{++mSavedResourceCount} \"{args.ResourceFileName}\"");

        string extension = Path.GetExtension(args.ResourceFileName);
        switch (extension)
        {
            case ".ttf":
            case ".woff":
            {
                // Por defecto, 'ResourceFileUri' usa la carpeta del sistema para las fuentes.
                // Para evitar problemas en otras plataformas, debe especificar explícitamente la ruta de las fuentes.
                args.ResourceFileUri = ArtifactsDir + Path.DirectorySeparatorChar + args.ResourceFileName;
                break;
            }
        }

        mText.AppendLine("\t" + args.ResourceFileUri);

        // Si hemos especificado una carpeta en la propiedad "ResourcesFolderAlias",
        // también necesitaremos redirigir cada flujo para poner su recurso en esa carpeta.
        args.ResourceStream = new FileStream(args.ResourceFileUri, FileMode.Create);
        args.KeepResourceStreamOpen = false;
    }

    public string GetText()
    {
        return mText.ToString();
    }

    private int mSavedResourceCount;
    private readonly StringBuilder mText = new StringBuilder();
}
```

### Ver también

* class [HtmlFixedSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* asamblea [Aspose.Words](../../../)


