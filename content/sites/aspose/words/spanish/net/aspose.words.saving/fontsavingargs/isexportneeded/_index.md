---
title: FontSavingArgs.IsExportNeeded
second_title: Referencia de API de Aspose.Words para .NET
description: FontSavingArgs propiedad. Permite especificar si la fuente actual se exportará como recurso de fuente. El valor predeterminado esverdadero .
type: docs
weight: 60
url: /es/net/aspose.words.saving/fontsavingargs/isexportneeded/
---
## FontSavingArgs.IsExportNeeded property

Permite especificar si la fuente actual se exportará como recurso de fuente. El valor predeterminado es`verdadero` .

```csharp
public bool IsExportNeeded { get; set; }
```

### Ejemplos

Muestra cómo definir una lógica personalizada para exportar fuentes al guardar en HTML.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Configure un objeto SaveOptions para exportar fuentes a archivos separados.
    // Establezca una devolución de llamada que manejará el guardado de fuentes de manera personalizada.
    HtmlSaveOptions options = new HtmlSaveOptions
    {
        ExportFontResources = true,
        FontSavingCallback = new HandleFontSaving()
    };

    // La devolución de llamada exportará archivos .ttf y los guardará junto con el documento de salida.
    doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveExportedFonts.html", options);

    foreach (string fontFilename in Array.FindAll(Directory.GetFiles(ArtifactsDir), s => s.EndsWith(".ttf")))
    {
        Console.WriteLine(fontFilename);
    }

/// <summary>
/// Imprime información sobre las fuentes exportadas y las guarda en la misma carpeta del sistema local que su salida .html.
/// </summary>
public class HandleFontSaving : IFontSavingCallback
{
    void IFontSavingCallback.FontSaving(FontSavingArgs args)
    {
        Console.Write($"Font:\t{args.FontFamilyName}");
        if (args.Bold) Console.Write(", bold");
        if (args.Italic) Console.Write(", italic");
        Console.WriteLine($"\nSource:\t{args.OriginalFileName}, {args.OriginalFileSize} bytes\n");

        // También podemos acceder al documento fuente desde aquí.
        Assert.True(args.Document.OriginalFileName.EndsWith("Rendering.docx"));

        Assert.True(args.IsExportNeeded);
        Assert.True(args.IsSubsettingNeeded);

        // Hay dos formas de guardar una fuente exportada.
        // 1 - Guárdelo en una ubicación del sistema de archivos local:
        args.FontFileName = args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last();

        // 2 - Guardarlo en una secuencia:
        args.FontStream =
            new FileStream(ArtifactsDir + args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last(), FileMode.Create);
        Assert.False(args.KeepFontStreamOpen);
    }
}
```

### Ver también

* class [FontSavingArgs](../)
* espacio de nombres [Aspose.Words.Saving](../../fontsavingargs/)
* asamblea [Aspose.Words](../../../)


