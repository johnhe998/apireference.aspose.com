---
title: SvgSaveOptions.ResourcesFolderAlias
second_title: Referencia de API de Aspose.Words para .NET
description: SvgSaveOptions propiedad. Especifica el nombre de la carpeta utilizada para construir los URI de imagen escritos en un documento SVG. El valor predeterminado esnulo .
type: docs
weight: 60
url: /es/net/aspose.words.saving/svgsaveoptions/resourcesfolderalias/
---
## SvgSaveOptions.ResourcesFolderAlias property

Especifica el nombre de la carpeta utilizada para construir los URI de imagen escritos en un documento SVG. El valor predeterminado es`nulo` .

```csharp
public string ResourcesFolderAlias { get; set; }
```

### Observaciones

Cuando guardas un[`Document`](../../../aspose.words/document/)en formato SVG, Aspose.Words necesita guardar todas las imágenes incrustadas en el documento como archivos independientes.[`ResourcesFolder`](../resourcesfolder/) le permite especificar dónde se guardarán las imágenes y`ResourcesFolderAlias` permite especificar cómo se construirán las URI de la imagen.

### Ejemplos

Muestra cómo manipular e imprimir los URI de los recursos vinculados creados al convertir un documento a .svg.

```csharp
public void SvgResourceFolder()
{
    Document doc = new Document(MyDir + "Rendering.docx");

    SvgSaveOptions options = new SvgSaveOptions
    {
        SaveFormat = SaveFormat.Svg,
        ExportEmbeddedImages = false,
        ResourcesFolder = ArtifactsDir + "SvgResourceFolder",
        ResourcesFolderAlias = ArtifactsDir + "SvgResourceFolderAlias",
        ShowPageBorder = false,

        ResourceSavingCallback = new ResourceUriPrinter()
    };

    Directory.CreateDirectory(options.ResourcesFolderAlias);

    doc.Save(ArtifactsDir + "SvgSaveOptions.SvgResourceFolder.svg", options);
}

/// <summary>
/// Cuenta e imprime los URI de los recursos contenidos en cuando se convierten a .svg.
/// </summary>
private class ResourceUriPrinter : IResourceSavingCallback
{
    void IResourceSavingCallback.ResourceSaving(ResourceSavingArgs args)
    {
        Console.WriteLine($"Resource #{++mSavedResourceCount} \"{args.ResourceFileName}\"");
        Console.WriteLine("\t" + args.ResourceFileUri);
    }

    private int mSavedResourceCount;
}
```

### Ver también

* class [SvgSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../svgsaveoptions/)
* asamblea [Aspose.Words](../../../)


