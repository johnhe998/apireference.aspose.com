---
title: LoadOptions.BaseUri
second_title: Referencia de API de Aspose.Words para .NET
description: LoadOptions propiedad. Obtiene o establece la cadena que se usará para convertir los URI relativos encontrados en el documento en URI absolutos cuando sea necesario. Puede ser una cadena nula o vacía. El valor predeterminado es nulo.
type: docs
weight: 20
url: /es/net/aspose.words.loading/loadoptions/baseuri/
---
## LoadOptions.BaseUri property

Obtiene o establece la cadena que se usará para convertir los URI relativos encontrados en el documento en URI absolutos cuando sea necesario. Puede ser una cadena nula o vacía. El valor predeterminado es nulo.

```csharp
public string BaseUri { get; set; }
```

### Observaciones

Esta propiedad se utiliza para convertir URI relativos en absolutos en los siguientes casos:

1. Al cargar un documento HTML desde una secuencia y el documento contiene imágenes con URI relativos y no tiene un URI base especificado en el elemento BASE HTML.
2. Al guardar un documento en PDF y otros formatos, para recuperar imágenes vinculadas mediante URI relativos para que las imágenes se puedan guardar en el documento de salida.

### Ejemplos

Muestra cómo abrir un documento HTML con imágenes de una transmisión usando un URI base.

```csharp
using (Stream stream = File.OpenRead(MyDir + "Document.html"))
{
    // Pasar la URI de la carpeta base mientras se carga
    // para que se puedan encontrar todas las imágenes con URI relativas en el documento HTML.
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.BaseUri = ImageDir;

    Document doc = new Document(stream, loadOptions);

    // Verifica que la primera forma del documento contenga una imagen válida.
    Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

    Assert.IsTrue(shape.IsImage);
    Assert.IsNotNull(shape.ImageData.ImageBytes);
    Assert.AreEqual(32.0, ConvertUtil.PointToPixel(shape.Width), 0.01);
    Assert.AreEqual(32.0, ConvertUtil.PointToPixel(shape.Height), 0.01);
}
```

### Ver también

* class [LoadOptions](../)
* espacio de nombres [Aspose.Words.Loading](../../loadoptions/)
* asamblea [Aspose.Words](../../../)


