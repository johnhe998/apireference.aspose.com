---
title: Class PageSavingArgs
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Saving.PageSavingArgs clase. Proporciona datos para elPageSaving evento.
type: docs
weight: 5100
url: /es/net/aspose.words.saving/pagesavingargs/
---
## PageSavingArgs class

Proporciona datos para el[`PageSaving`](../ipagesavingcallback/pagesaving/) evento.

```csharp
public class PageSavingArgs
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [PageSavingArgs](pagesavingargs/)() | Constructor predeterminado |

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [KeepPageStreamOpen](../../aspose.words.saving/pagesavingargs/keeppagestreamopen/) { get; set; } | Especifica si Aspose.Words debe mantener la transmisión abierta o cerrarla después de guardar una página del documento. |
| [PageFileName](../../aspose.words.saving/pagesavingargs/pagefilename/) { get; set; } | Obtiene o establece el nombre del archivo en el que se guardará la página del documento. |
| [PageIndex](../../aspose.words.saving/pagesavingargs/pageindex/) { get; } | Índice de la página actual. |
| [PageStream](../../aspose.words.saving/pagesavingargs/pagestream/) { get; set; } | Permite especificar la secuencia donde se guardará la página del documento. |

### Ejemplos

Muestra cómo usar una devolución de llamada para guardar un documento en HTML página por página.

```csharp
public void PageFileNames()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Writeln("Page 1.");
    builder.InsertBreak(BreakType.PageBreak);
    builder.Writeln("Page 2.");
    builder.InsertImage(ImageDir + "Logo.jpg");
    builder.InsertBreak(BreakType.PageBreak);
    builder.Writeln("Page 3.");

    // Crear un objeto "HtmlFixedSaveOptions", que podemos pasar al método "Guardar" del documento
    // para modificar cómo convertimos el documento a HTML.
    HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions();

    // Guardaremos cada página de este documento en un archivo HTML separado en el sistema de archivos local.
    // Establecer una devolución de llamada que nos permita nombrar cada documento HTML de salida.
    htmlFixedSaveOptions.PageSavingCallback = new CustomFileNamePageSavingCallback();

    doc.Save(ArtifactsDir + "SavingCallback.PageFileNames.html", htmlFixedSaveOptions);

    string[] filePaths = Directory.GetFiles(ArtifactsDir).Where(
        s => s.StartsWith(ArtifactsDir + "SavingCallback.PageFileNames.Page_")).OrderBy(s => s).ToArray();

    Assert.AreEqual(3, filePaths.Length);
}

/// <summary>
/// Guarda todas las páginas en un archivo y directorio especificado dentro.
/// </summary>
private class CustomFileNamePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        string outFileName = $"{ArtifactsDir}SavingCallback.PageFileNames.Page_{args.PageIndex}.html";

        // A continuación hay dos formas de especificar dónde Aspose.Words guardará cada página del documento.
        // 1 - Establecer un nombre de archivo para el archivo de la página de salida:
        args.PageFileName = outFileName;

        // 2 - Crea una transmisión personalizada para el archivo de la página de salida:
        args.PageStream = new FileStream(outFileName, FileMode.Create);

        Assert.False(args.KeepPageStreamOpen);
    }
}
```

### Ver también

* espacio de nombres [Aspose.Words.Saving](../../aspose.words.saving/)
* asamblea [Aspose.Words](../../)


