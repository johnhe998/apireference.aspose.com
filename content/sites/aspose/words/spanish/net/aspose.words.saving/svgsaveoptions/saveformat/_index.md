---
title: SvgSaveOptions.SaveFormat
second_title: Referencia de API de Aspose.Words para .NET
description: SvgSaveOptions propiedad. Especifica el formato en el que se guardará el documento si se utiliza este objeto de opciones de guardado. Solo se puedeSvg .
type: docs
weight: 70
url: /es/net/aspose.words.saving/svgsaveoptions/saveformat/
---
## SvgSaveOptions.SaveFormat property

Especifica el formato en el que se guardará el documento si se utiliza este objeto de opciones de guardado. Solo se puedeSvg .

```csharp
public override SaveFormat SaveFormat { get; set; }
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

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [SvgSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../svgsaveoptions/)
* asamblea [Aspose.Words](../../../)


