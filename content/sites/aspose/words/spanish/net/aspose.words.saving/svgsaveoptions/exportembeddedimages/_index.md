---
title: SvgSaveOptions.ExportEmbeddedImages
second_title: Referencia de API de Aspose.Words para .NET
description: SvgSaveOptions propiedad. Especificado si las imágenes deben incrustarse en el documento SVG como base64. Tenga en cuenta que establecer este indicador puede aumentar significativamente el tamaño del archivo SVG de salida.
type: docs
weight: 20
url: /es/net/aspose.words.saving/svgsaveoptions/exportembeddedimages/
---
## SvgSaveOptions.ExportEmbeddedImages property

Especificado si las imágenes deben incrustarse en el documento SVG como base64. Tenga en cuenta que establecer este indicador puede aumentar significativamente el tamaño del archivo SVG de salida.

```csharp
public bool ExportEmbeddedImages { get; set; }
```

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


