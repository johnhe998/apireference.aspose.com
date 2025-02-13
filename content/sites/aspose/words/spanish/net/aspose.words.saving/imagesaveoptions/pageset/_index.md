---
title: ImageSaveOptions.PageSet
second_title: Referencia de API de Aspose.Words para .NET
description: ImageSaveOptions propiedad. Obtiene o establece las páginas a representar. El valor predeterminado es todas las páginas del documento.
type: docs
weight: 90
url: /es/net/aspose.words.saving/imagesaveoptions/pageset/
---
## ImageSaveOptions.PageSet property

Obtiene o establece las páginas a representar. El valor predeterminado es todas las páginas del documento.

```csharp
public PageSet PageSet { get; set; }
```

### Observaciones

Esta propiedad solo tiene efecto cuando se procesan páginas de documentos. Esta propiedad se ignora al representar formas en imágenes.

### Ejemplos

Muestra cómo extraer páginas en función de intervalos de páginas exactos.

```csharp
Document doc = new Document(MyDir + "Images.docx");

ImageSaveOptions imageOptions = new ImageSaveOptions(SaveFormat.Tiff);
PageSet pageSet = new PageSet(new PageRange(1, 1), new PageRange(2, 3), new PageRange(1, 3),
    new PageRange(2, 4), new PageRange(1, 1));

imageOptions.PageSet = pageSet;
doc.Save(ArtifactsDir + "ImageSaveOptions.ExportVariousPageRanges.tiff", imageOptions);
```

Muestra cómo representar cada página de un documento en una imagen TIFF separada.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2.");
builder.InsertImage(ImageDir + "Logo.jpg");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 3.");

// Crea un objeto "ImageSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar la forma en que ese método convierte el documento en una imagen.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff);

for (int i = 0; i < doc.PageCount; i++)
{
    // Establecer la propiedad "PageSet" en el número de la primera página desde
    // desde donde comenzar a renderizar el documento.
    options.PageSet = new PageSet(i);

    doc.Save(ArtifactsDir + $"ImageSaveOptions.PageByPage.{i + 1}.tiff", options);
}
```

Muestra cómo especificar qué página de un documento representar como una imagen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world! This is page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("This is page 3.");

Assert.AreEqual(3, doc.PageCount);

// Cuando guardamos el documento como una imagen, Aspose.Words solo muestra la primera página por defecto.
// Podemos pasar un objeto SaveOptions para especificar una página diferente para representar.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Gif);

// Representa cada página del documento en un archivo de imagen separado.
for (int i = 1; i <= doc.PageCount; i++)
{
    saveOptions.PageSet = new PageSet(1);

    doc.Save(ArtifactsDir + $"ImageSaveOptions.PageIndex.Page {i}.gif", saveOptions);
}
```

Muestra cómo representar una página de un documento a una imagen JPEG.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2.");
builder.InsertImage(ImageDir + "Logo.jpg");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 3.");

// Crea un objeto "ImageSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar la forma en que ese método convierte el documento en una imagen.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Establezca el "PageSet" en "1" para seleccionar la segunda página a través de
// el índice de base cero desde el que empezar a representar el documento.
options.PageSet = new PageSet(1);

// Cuando guardamos el documento en formato JPEG, Aspose.Words solo muestra una página.
// Esta imagen contendrá una página a partir de la página dos,
// que será solo la segunda página del documento original.
doc.Save(ArtifactsDir + "ImageSaveOptions.OnePage.jpg", options);
```

### Ver también

* class [PageSet](../../pageset/)
* class [ImageSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../imagesaveoptions/)
* asamblea [Aspose.Words](../../../)


