---
title: PdfLoadOptions.SkipPdfImages
second_title: Referencia de API de Aspose.Words para .NET
description: PdfLoadOptions propiedad. Obtiene o establece el indicador que indica si las imágenes deben omitirse al cargar un documento PDF. El valor predeterminado es Falso.
type: docs
weight: 40
url: /es/net/aspose.words.loading/pdfloadoptions/skippdfimages/
---
## PdfLoadOptions.SkipPdfImages property

Obtiene o establece el indicador que indica si las imágenes deben omitirse al cargar un documento PDF. El valor predeterminado es Falso.

```csharp
public bool SkipPdfImages { get; set; }
```

### Ejemplos

Muestra cómo omitir imágenes durante la carga de archivos PDF.

```csharp
PdfLoadOptions options = new PdfLoadOptions();
options.SkipPdfImages = isSkipPdfImages;

Document doc = new Document(MyDir + "Images.pdf", options);
NodeCollection shapeCollection = doc.GetChildNodes(NodeType.Shape, true);

if (isSkipPdfImages)
{
    Assert.AreEqual(shapeCollection.Count, 0);
}
else
{
    Assert.AreNotEqual(shapeCollection.Count, 0);
}
```

### Ver también

* class [PdfLoadOptions](../)
* espacio de nombres [Aspose.Words.Loading](../../pdfloadoptions/)
* asamblea [Aspose.Words](../../../)


