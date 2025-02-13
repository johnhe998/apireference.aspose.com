---
title: Enum MetafileRenderingMode
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Saving.MetafileRenderingMode enumeración. Especifica cómo Aspose.Words debe representar los metarchivos WMF y EMF.
type: docs
weight: 5010
url: /es/net/aspose.words.saving/metafilerenderingmode/
---
## MetafileRenderingMode enumeration

Especifica cómo Aspose.Words debe representar los metarchivos WMF y EMF.

```csharp
public enum MetafileRenderingMode
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| VectorWithFallback | `0` | Aspose.Words intenta representar un metarchivo como gráficos vectoriales. Si Aspose.Words no puede representar correctamente algunos de los registros del metarchivo en gráficos vectoriales, entonces Aspose.Words representa este metarchivo en un mapa de bits. |
| Vector | `1` | Aspose.Words representa un metarchivo como gráficos vectoriales. |
| Bitmap | `2` | Aspose.Words invoca GDI+ para representar un metarchivo en un mapa de bits y luego guarda el mapa de bits en el documento de salida. |

### Ejemplos

Los espectáculos agregaron una alternativa a la representación de mapas de bits y cambiaron el tipo de advertencias sobre registros de metarchivos no admitidos.

```csharp
{
    Document doc = new Document(MyDir + "WMF with image.docx");

    MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions();

    // Establezca la propiedad "EmulateRasterOperations" en "false" para volver al mapa de bits cuando
    // encuentra un metarchivo, que requerirá operaciones de trama para representar en el PDF de salida.
    metafileRenderingOptions.EmulateRasterOperations = false;

    // Establezca la propiedad "RenderingMode" en "VectorWithFallback" para intentar representar cada metarchivo utilizando gráficos vectoriales.
    metafileRenderingOptions.RenderingMode = MetafileRenderingMode.VectorWithFallback;

    // Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
    // para modificar cómo ese método convierte el documento a .PDF y aplica la configuración
    // en nuestro objeto MetafileRenderingOptions para la operación de guardado.
    PdfSaveOptions saveOptions = new PdfSaveOptions();
    saveOptions.MetafileRenderingOptions = metafileRenderingOptions;

    HandleDocumentWarnings callback = new HandleDocumentWarnings();
    doc.WarningCallback = callback;

    doc.Save(ArtifactsDir + "PdfSaveOptions.HandleBinaryRasterWarnings.pdf", saveOptions);

    Assert.AreEqual(1, callback.Warnings.Count);
    Assert.AreEqual("'R2_XORPEN' binary raster operation is partly supported.",
        callback.Warnings[0].Description);
}

/// <summary>
/// Imprime y recopila advertencias relacionadas con la pérdida de formato que se producen al guardar un documento.
/// </summary>
public class HandleDocumentWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.MinorFormattingLoss)
        {
            Console.WriteLine("Unsupported operation: " + info.Description);
            Warnings.Warning(info);
        }
    }

    public WarningInfoCollection Warnings = new WarningInfoCollection();
}
```

### Ver también

* espacio de nombres [Aspose.Words.Saving](../../aspose.words.saving/)
* asamblea [Aspose.Words](../../)


