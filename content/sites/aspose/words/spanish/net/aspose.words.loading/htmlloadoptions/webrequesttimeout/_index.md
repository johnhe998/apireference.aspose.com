---
title: HtmlLoadOptions.WebRequestTimeout
second_title: Referencia de API de Aspose.Words para .NET
description: HtmlLoadOptions propiedad. El número de milisegundos a esperar antes de que se agote el tiempo de espera de la solicitud web. El valor predeterminado es 100000 milisegundos 100 segundos.
type: docs
weight: 70
url: /es/net/aspose.words.loading/htmlloadoptions/webrequesttimeout/
---
## HtmlLoadOptions.WebRequestTimeout property

El número de milisegundos a esperar antes de que se agote el tiempo de espera de la solicitud web. El valor predeterminado es 100000 milisegundos (100 segundos).

```csharp
public int WebRequestTimeout { get; set; }
```

### Observaciones

El número de milisegundos que Aspose.Words espera una respuesta, al cargar recursos externos (imágenes, hojas de estilo ) vinculados en documentos HTML y MHTML.

### Ejemplos

Muestra cómo establecer un límite de tiempo para las solicitudes web al cargar un documento con recursos externos vinculados por URL.

```csharp
{
    // Cree un nuevo objeto HtmlLoadOptions y verifique su umbral de tiempo de espera para una solicitud web.
    HtmlLoadOptions options = new HtmlLoadOptions();

    // Al cargar un documento Html con recursos vinculados externamente por una URL de dirección web,
    // Aspose.Words anulará las solicitudes web que no obtengan los recursos dentro de este límite de tiempo, en milisegundos.
    Assert.AreEqual(100000, options.WebRequestTimeout);

    // Establecer un WarningCallback que registrará todas las advertencias que se produzcan durante la carga.
    ListDocumentWarnings warningCallback = new ListDocumentWarnings();
    options.WarningCallback = warningCallback;

    // Cargue dicho documento y verifique que se haya creado una forma con datos de imagen.
    // Esta imagen vinculada requerirá una solicitud web para cargarse, que deberá completarse dentro de nuestro límite de tiempo.
    string html = $@"
        <html>
            <img src=""{ImageUrl}"" alt=""Aspose logo"" style=""width:400px;height:400px;"">
        </html>
    ";

    // Establezca un límite de tiempo de espera no razonable e intente cargar el documento nuevamente.
    options.WebRequestTimeout = 0;
    Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), options);
    Assert.AreEqual(2, warningCallback.Warnings().Count);

    // Una solicitud web que no puede obtener una imagen dentro del límite de tiempo aún producirá una imagen.
    // Sin embargo, la imagen será la 'x' roja que comúnmente significa que faltan imágenes.
    Shape imageShape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
    Assert.AreEqual(924, imageShape.ImageData.ImageBytes.Length);

    // También podemos configurar una devolución de llamada personalizada para recoger cualquier advertencia de solicitudes web agotadas.
    Assert.AreEqual(WarningSource.Html, warningCallback.Warnings()[0].Source);
    Assert.AreEqual(WarningType.DataLoss, warningCallback.Warnings()[0].WarningType);
    Assert.AreEqual($"Couldn't load a resource from \'{ImageUrl}\'.", warningCallback.Warnings()[0].Description);

    Assert.AreEqual(WarningSource.Html, warningCallback.Warnings()[1].Source);
    Assert.AreEqual(WarningType.DataLoss, warningCallback.Warnings()[1].WarningType);
    Assert.AreEqual("Image has been replaced with a placeholder.", warningCallback.Warnings()[1].Description);

    doc.Save(ArtifactsDir + "HtmlLoadOptions.WebRequestTimeout.docx");
}

/// <summary>
/// Almacena todas las advertencias que ocurren durante una operación de carga de documentos en una Lista.
/// </summary>
private class ListDocumentWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        mWarnings.Add(info);
    }

    public List<WarningInfo> Warnings() { 
        return mWarnings;
    }

    private readonly List<WarningInfo> mWarnings = new List<WarningInfo>();
}
```

### Ver también

* class [HtmlLoadOptions](../)
* espacio de nombres [Aspose.Words.Loading](../../htmlloadoptions/)
* asamblea [Aspose.Words](../../../)


