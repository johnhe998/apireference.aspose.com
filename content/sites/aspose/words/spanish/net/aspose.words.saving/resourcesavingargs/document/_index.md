---
title: ResourceSavingArgs.Document
second_title: Referencia de API de Aspose.Words para .NET
description: ResourceSavingArgs propiedad. Obtiene el objeto de documento que se está guardando actualmente.
type: docs
weight: 10
url: /es/net/aspose.words.saving/resourcesavingargs/document/
---
## ResourceSavingArgs.Document property

Obtiene el objeto de documento que se está guardando actualmente.

```csharp
public Document Document { get; }
```

### Ejemplos

Muestra cómo utilizar una devolución de llamada para realizar un seguimiento de los recursos externos creados al convertir un documento a HTML.

```csharp
public void ResourceSavingCallback()
{
    Document doc = new Document(MyDir + "Bullet points with alternative font.docx");

    FontSavingCallback callback = new FontSavingCallback();

    HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions
    {
        ResourceSavingCallback = callback
    };

    doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.UsingMachineFonts.html", saveOptions);

    Console.WriteLine(callback.GetText());
}

private class FontSavingCallback : IResourceSavingCallback
{
    /// <summary>
    /// Llamado cuando Aspose.Words guarda un recurso externo en una página fija HTML o SVG.
    /// </summary>
    public void ResourceSaving(ResourceSavingArgs args)
    {
        mText.AppendLine($"Original document URI:\t{args.Document.OriginalFileName}");
        mText.AppendLine($"Resource being saved:\t{args.ResourceFileName}");
        mText.AppendLine($"Full uri after saving:\t{args.ResourceFileUri}\n");
    }

    public string GetText()
    {
        return mText.ToString();
    }

    private readonly StringBuilder mText = new StringBuilder();
}
```

### Ver también

* class [Document](../../../aspose.words/document/)
* class [ResourceSavingArgs](../)
* espacio de nombres [Aspose.Words.Saving](../../resourcesavingargs/)
* asamblea [Aspose.Words](../../../)


