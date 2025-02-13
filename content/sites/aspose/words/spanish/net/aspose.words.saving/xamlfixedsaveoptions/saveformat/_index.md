---
title: XamlFixedSaveOptions.SaveFormat
second_title: Referencia de API de Aspose.Words para .NET
description: XamlFixedSaveOptions propiedad. Especifica el formato en el que se guardará el documento si se utiliza este objeto de opciones de guardado. Solo se puedeXamlFixed .
type: docs
weight: 50
url: /es/net/aspose.words.saving/xamlfixedsaveoptions/saveformat/
---
## XamlFixedSaveOptions.SaveFormat property

Especifica el formato en el que se guardará el documento si se utiliza este objeto de opciones de guardado. Solo se puedeXamlFixed .

```csharp
public override SaveFormat SaveFormat { get; set; }
```

### Ejemplos

Muestra cómo imprimir los URI de los recursos vinculados creados al convertir un documento a .xaml de formato fijo.

```csharp
public void ResourceFolder()
{
    Document doc = new Document(MyDir + "Rendering.docx");
    ResourceUriPrinter callback = new ResourceUriPrinter();

    // Crear un objeto "XamlFixedSaveOptions", que podemos pasar al método "Guardar" del documento
    // para modificar cómo guardamos el documento en el formato de guardado XAML.
    XamlFixedSaveOptions options = new XamlFixedSaveOptions();

    Assert.AreEqual(SaveFormat.XamlFixed, options.SaveFormat);

    // Use la propiedad "ResourcesFolder" para asignar una carpeta en el sistema de archivos local en la que
    // Aspose.Words guardará todos los recursos vinculados del documento, como imágenes y fuentes.
    options.ResourcesFolder = ArtifactsDir + "XamlFixedResourceFolder";

    // Usa la propiedad "ResourcesFolderAlias" para usar esta carpeta
    // al construir URI de imagen en lugar del nombre de la carpeta de recursos.
    options.ResourcesFolderAlias = ArtifactsDir + "XamlFixedFolderAlias";

    options.ResourceSavingCallback = callback;

    // Una carpeta especificada por "ResourcesFolderAlias" deberá contener los recursos en lugar de "ResourcesFolder".
    // Debemos asegurarnos de que la carpeta exista antes de que los flujos de devolución de llamada puedan poner sus recursos en ella.
    Directory.CreateDirectory(options.ResourcesFolderAlias);

    doc.Save(ArtifactsDir + "XamlFixedSaveOptions.ResourceFolder.xaml", options);

    foreach (string resource in callback.Resources)
        Console.WriteLine(resource);
}

/// <summary>
/// Cuenta e imprime URI de recursos creados durante la conversión a .xaml fijo.
/// </summary>
private class ResourceUriPrinter : IResourceSavingCallback
{
    public ResourceUriPrinter()
    {
        Resources = new List<string>();
    }

    void IResourceSavingCallback.ResourceSaving(ResourceSavingArgs args)
    {
        Resources.Add($"Resource \"{args.ResourceFileName}\"\n\t{args.ResourceFileUri}");

        // Si especificamos un alias de carpeta de recursos, también necesitaríamos
        // para redirigir cada flujo para poner su recurso en la carpeta de alias.
        args.ResourceStream = new FileStream(args.ResourceFileUri, FileMode.Create);
        args.KeepResourceStreamOpen = false;
    }

    public List<string> Resources { get; }
}
```

### Ver también

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [XamlFixedSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../xamlfixedsaveoptions/)
* asamblea [Aspose.Words](../../../)


