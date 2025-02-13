---
title: HtmlSaveOptions.ExportFontResources
second_title: Referencia de API de Aspose.Words para .NET
description: HtmlSaveOptions propiedad. Especifica si los recursos de fuentes deben exportarse a HTML MHTML o EPUB. El valor predeterminado esfalso .
type: docs
weight: 150
url: /es/net/aspose.words.saving/htmlsaveoptions/exportfontresources/
---
## HtmlSaveOptions.ExportFontResources property

Especifica si los recursos de fuentes deben exportarse a HTML, MHTML o EPUB. El valor predeterminado es`falso` .

```csharp
public bool ExportFontResources { get; set; }
```

### Observaciones

La exportación de recursos de fuentes permite la representación coherente de documentos independientemente de las fuentes disponibles en el entorno de un usuario determinado.

Si`ExportFontResources` se establece en`verdadero` , el documento HTML principal se referirá a cada fuente a través de el CSS 3 **@Perfil delantero**La regla at y las fuentes se generarán como archivos separados. Al exportar a formatos IDPF EPUB o MHTML , las fuentes se incrustarán en el paquete correspondiente junto con otros archivos subsidiarios.

Si[`ExportFontsAsBase64`](../exportfontsasbase64/) se establece en`verdadero` , las fuentes no se guardarán en archivos separados. En su lugar, se incrustarán en **@Perfil delantero** Reglas at en la codificación Base64.

**¡Importante!** Al exportar recursos de fuentes, se deben considerar los problemas de licencia de fuentes. Los autores que deseen utilizar fuentes específicas a través de un mecanismo de fuente downloadable siempre deben verificar cuidadosamente que su uso previsto esté dentro del alcance de la licencia de la fuente. Actualmente, muchas fuentes comerciales no permiten la descarga web de sus fuentes de ninguna forma. Los acuerdos de licencia que cubren algunas fuentes señalan específicamente que el uso a través de **@Perfil delantero** No se permiten las reglas en las hojas de estilo CSS. La creación de subconjuntos de fuentes también puede infringir los términos de la licencia.

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

* class [HtmlSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../htmlsaveoptions/)
* asamblea [Aspose.Words](../../../)


