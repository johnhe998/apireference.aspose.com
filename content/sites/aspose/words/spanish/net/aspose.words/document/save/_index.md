---
title: Document.Save
second_title: Referencia de API de Aspose.Words para .NET
description: Document método. Guarda el documento en un archivo. Determina automáticamente el formato de guardado de la extensión.
type: docs
weight: 680
url: /es/net/aspose.words/document/save/
---
## Save(string) {#save_2}

Guarda el documento en un archivo. Determina automáticamente el formato de guardado de la extensión.

```csharp
public SaveOutputParameters Save(string fileName)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| fileName | String | El nombre del documento. Si ya existe un documento con el nombre de archivo especificado , se sobrescribe el documento existente. |

### Valor_devuelto

Información adicional que puede utilizar opcionalmente.

### Ejemplos

Muestra cómo abrir un documento y convertirlo a .PDF.

```csharp
Document doc = new Document(MyDir + "Document.docx");

doc.Save(ArtifactsDir + "Document.ConvertToPdf.pdf");
```

Muestra cómo convertir un PDF a un .docx.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Hello world!");

doc.Save(ArtifactsDir + "PDF2Word.ConvertPdfToDocx.pdf");

// Cargue el documento PDF que acabamos de guardar y conviértalo a .docx.
Document pdfDoc = new Document(ArtifactsDir + "PDF2Word.ConvertPdfToDocx.pdf");

pdfDoc.Save(ArtifactsDir + "PDF2Word.ConvertPdfToDocx.docx");
```

### Ver también

* class [SaveOutputParameters](../../../aspose.words.saving/saveoutputparameters/)
* class [Document](../)
* espacio de nombres [Aspose.Words](../../document/)
* asamblea [Aspose.Words](../../../)

---

## Save(string, SaveFormat) {#save_3}

Guarda el documento en un archivo en el formato especificado.

```csharp
public SaveOutputParameters Save(string fileName, SaveFormat saveFormat)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| fileName | String | El nombre del documento. Si ya existe un documento con el nombre de archivo especificado , se sobrescribe el documento existente. |
| saveFormat | SaveFormat | El formato en el que guardar el documento. |

### Valor_devuelto

Información adicional que puede utilizar opcionalmente.

### Ejemplos

Muestra cómo convertir de formato DOCX a HTML.

```csharp
Document doc = new Document(MyDir + "Document.docx");

doc.Save(ArtifactsDir + "Document.ConvertToHtml.html", SaveFormat.Html);
```

### Ver también

* class [SaveOutputParameters](../../../aspose.words.saving/saveoutputparameters/)
* enum [SaveFormat](../../saveformat/)
* class [Document](../)
* espacio de nombres [Aspose.Words](../../document/)
* asamblea [Aspose.Words](../../../)

---

## Save(string, SaveOptions) {#save_4}

Guarda el documento en un archivo usando las opciones de guardado especificadas.

```csharp
public SaveOutputParameters Save(string fileName, SaveOptions saveOptions)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| fileName | String | El nombre del documento. Si ya existe un documento con el nombre de archivo especificado , se sobrescribe el documento existente. |
| saveOptions | SaveOptions | Especifica las opciones que controlan cómo se guarda el documento. Puede ser nulo. |

### Valor_devuelto

Información adicional que puede utilizar opcionalmente.

### Ejemplos

Muestra cómo mejorar la calidad de un documento renderizado con SaveOptions.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 60;
builder.Writeln("Some text.");

SaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

doc.Save(ArtifactsDir + "Document.ImageSaveOptions.Default.jpg", options);

options.UseAntiAliasing = true;
options.UseHighQualityRendering = true;

doc.Save(ArtifactsDir + "Document.ImageSaveOptions.HighQuality.jpg", options);
```

Muestra cómo convertir un PDF a .docx y personalizar el proceso de guardado con un objeto SaveOptions.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

doc.Save(ArtifactsDir + "PDF2Word.ConvertPdfToDocxCustom.pdf");

// Cargue el documento PDF que acabamos de guardar y conviértalo a .docx.
Document pdfDoc = new Document(ArtifactsDir + "PDF2Word.ConvertPdfToDocxCustom.pdf");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx);

// Establecer la propiedad "Contraseña" para cifrar el documento guardado con una contraseña.
saveOptions.Password = "MyPassword";

pdfDoc.Save(ArtifactsDir + "PDF2Word.ConvertPdfToDocxCustom.docx", saveOptions);
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

Muestra cómo configurar la compresión al guardar un documento como JPEG.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertImage(ImageDir + "Logo.jpg");

// Crea un objeto "ImageSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar la forma en que ese método convierte el documento en una imagen.
ImageSaveOptions imageOptions = new ImageSaveOptions(SaveFormat.Jpeg);

// Establezca la propiedad "JpegQuality" en "10" para usar una compresión más fuerte al renderizar el documento.
// Esto reducirá el tamaño del archivo del documento, pero la imagen mostrará artefactos de compresión más prominentes.
imageOptions.JpegQuality = 10;

doc.Save(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighCompression.jpg", imageOptions);

Assert.That(20000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighCompression.jpg").Length));

// Establezca la propiedad "JpegQuality" en "100" para usar una compresión más débil al procesar el documento.
// Esto mejorará la calidad de la imagen a costa de aumentar el tamaño del archivo.
imageOptions.JpegQuality = 100;

doc.Save(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighQuality.jpg", imageOptions);

Assert.That(60000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighQuality.jpg").Length));
```

Muestra cómo convertir un documento completo a PDF con tres niveles en el esquema del documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar encabezados de niveles 1 a 5.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 1.2.1");
builder.Writeln("Heading 1.2.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading4;

builder.Writeln("Heading 1.2.2.1");
builder.Writeln("Heading 1.2.2.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading5;

builder.Writeln("Heading 1.2.2.2.1");
builder.Writeln("Heading 1.2.2.2.2");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// El documento PDF de salida contendrá un esquema, que es una tabla de contenido que enumera los encabezados en el cuerpo del documento.
// Al hacer clic en una entrada de este esquema, nos llevará a la ubicación de su respectivo encabezado.
// Establezca la propiedad "HeadingsOutlineLevels" en "4" para excluir todos los encabezados cuyos niveles estén por encima de 4 del esquema.
options.OutlineOptions.HeadingsOutlineLevels = 4;

// Si una entrada de esquema tiene entradas posteriores de un nivel superior entre ella y la siguiente entrada del mismo nivel o inferior,
// aparecerá una flecha a la izquierda de la entrada. Esta entrada es el "propietario" de varias de estas "subentradas".
// En nuestro documento, las entradas de esquema del 5.º nivel de encabezado son subentradas de la segunda entrada de esquema del 4.º nivel,
  // las entradas de nivel de encabezado 4 y 5 son subentradas de la segunda entrada de nivel 3, y así sucesivamente.
// En el esquema, podemos hacer clic en la flecha de la entrada "propietario" para colapsar/expandir todas sus subentradas.
// Establezca la propiedad "ExpandedOutlineLevels" en "2" para expandir automáticamente todas las entradas de encabezado de nivel 2 e inferior
 // y colapsar todas las entradas de nivel y 3 y superiores cuando abrimos el documento.
options.OutlineOptions.ExpandedOutlineLevels = 2;

doc.Save(ArtifactsDir + "PdfSaveOptions.ExpandedOutlineLevels.pdf", options);
```

### Ver también

* class [SaveOutputParameters](../../../aspose.words.saving/saveoutputparameters/)
* class [SaveOptions](../../../aspose.words.saving/saveoptions/)
* class [Document](../)
* espacio de nombres [Aspose.Words](../../document/)
* asamblea [Aspose.Words](../../../)

---

## Save(Stream, SaveFormat) {#save}

Guarda el documento en una secuencia utilizando el formato especificado.

```csharp
public SaveOutputParameters Save(Stream stream, SaveFormat saveFormat)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| stream | Stream | Transmitir dónde guardar el documento. |
| saveFormat | SaveFormat | El formato en el que guardar el documento. |

### Valor_devuelto

Información adicional que puede utilizar opcionalmente.

### Ejemplos

Muestra cómo guardar un documento en una secuencia.

```csharp
Document doc = new Document(MyDir + "Document.docx");

using (MemoryStream dstStream = new MemoryStream())
{
    doc.Save(dstStream, SaveFormat.Docx);

    // Verifique que la secuencia contenga el documento.
    Assert.AreEqual("Hello World!\r\rHello Word!\r\r\rHello World!", new Document(dstStream).GetText().Trim());
}
```

Muestra cómo guardar un documento en una imagen a través de una secuencia y luego leer la imagen de esa secuencia.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            builder.Font.Name = "Times New Roman";
            builder.Font.Size = 24;
            builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

            builder.InsertImage(ImageDir + "Logo.jpg");

#if NET48 || JAVA
            using (MemoryStream stream = new MemoryStream())
            {
                doc.Save(stream, SaveFormat.Bmp);

                stream.Position = 0;

                // Leer el flujo de nuevo en una imagen.
                using (Image image = Image.FromStream(stream))
                {
                    Assert.AreEqual(ImageFormat.Bmp, image.RawFormat);
                    Assert.AreEqual(816, image.Width);
                    Assert.AreEqual(1056, image.Height);
                }
            }
#elif NET5_0_OR_GREATER || __MOBILE__
            using (MemoryStream stream = new MemoryStream())
            {
                doc.Save(stream, SaveFormat.Bmp);

                stream.Position = 0;

                SKCodec codec = SKCodec.Create(stream);

                Assert.AreEqual(SKEncodedImageFormat.Bmp, codec.EncodedFormat);

                stream.Position = 0;

                using (SKBitmap image = SKBitmap.Decode(stream))
                {
                    Assert.AreEqual(816, image.Width);
                    Assert.AreEqual(1056, image.Height);
                }
            }
#endif
```

### Ver también

* class [SaveOutputParameters](../../../aspose.words.saving/saveoutputparameters/)
* enum [SaveFormat](../../saveformat/)
* class [Document](../)
* espacio de nombres [Aspose.Words](../../document/)
* asamblea [Aspose.Words](../../../)

---

## Save(Stream, SaveOptions) {#save_1}

Guarda el documento en una secuencia usando las opciones de guardado especificadas.

```csharp
public SaveOutputParameters Save(Stream stream, SaveOptions saveOptions)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| stream | Stream | Transmitir dónde guardar el documento. |
| saveOptions | SaveOptions | Especifica las opciones que controlan cómo se guarda el documento. Puede ser nulo. Si es nulo, el documento se guardará en formato DOC binario. |

### Valor_devuelto

Información adicional que puede utilizar opcionalmente.

### Ejemplos

Muestra cómo convertir solo algunas de las páginas de un documento a PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 3.");

using (Stream stream = File.Create(ArtifactsDir + "PdfSaveOptions.OnePage.pdf"))
{
    // Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
    // para modificar cómo ese método convierte el documento a .PDF.
    PdfSaveOptions options = new PdfSaveOptions();

    // Establezca "PageIndex" en "1" para representar una parte del documento a partir de la segunda página.
    options.PageSet = new PageSet(1);

    // Este documento contendrá una página a partir de la página dos, que solo contendrá la segunda página.
    doc.Save(stream, options);
}
```

### Ver también

* class [SaveOutputParameters](../../../aspose.words.saving/saveoutputparameters/)
* class [SaveOptions](../../../aspose.words.saving/saveoptions/)
* class [Document](../)
* espacio de nombres [Aspose.Words](../../document/)
* asamblea [Aspose.Words](../../../)

---

## Save(HttpResponse, string, ContentDisposition, SaveOptions) {#save_5}

Envía el documento al navegador del cliente.

```csharp
public SaveOutputParameters Save(HttpResponse response, string fileName, 
    ContentDisposition contentDisposition, SaveOptions saveOptions)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| response | HttpResponse | Objeto de respuesta donde guardar el documento. |
| fileName | String | El nombre del documento que aparecerá en el navegador del cliente. El nombre no debe contener la ruta. |
| contentDisposition | ContentDisposition | A[`ContentDisposition`](../../contentdisposition/) el valor that especifica cómo se presenta el documento en el navegador del cliente. |
| saveOptions | SaveOptions | Especifica las opciones que controlan cómo se guarda el documento. Puede ser nulo. |

### Valor_devuelto

Información adicional que puede utilizar opcionalmente.

### Observaciones

Internamente, este método primero guarda en un flujo de memoria y luego lo copia en el flujo de respuesta porque el flujo de respuesta no admite la búsqueda.

### Ejemplos

Muestra cómo realizar una combinación de correspondencia y luego guardar el documento en el navegador del cliente.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" MERGEFIELD FullName ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD Company ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD Address ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD City ");

doc.MailMerge.Execute(new string[] { "FullName", "Company", "Address", "City" },
    new object[] { "James Bond", "MI5 Headquarters", "Milbank", "London" });

// Envía el documento al navegador del cliente.
Assert.That(() => doc.Save(response, "Artifacts/MailMerge.ExecuteArray.docx", ContentDisposition.Inline, null),
    Throws.TypeOf<ArgumentNullException>()); //Lanzado porque HttpResponse es nulo en la prueba.

// Tendremos que cerrar esta respuesta manualmente para asegurarnos de no agregar ningún contenido superfluo al documento después de guardarlo.
Assert.That(() => response.End(), Throws.TypeOf<NullReferenceException>());
```

### Ver también

* class [SaveOutputParameters](../../../aspose.words.saving/saveoutputparameters/)
* enum [ContentDisposition](../../contentdisposition/)
* class [SaveOptions](../../../aspose.words.saving/saveoptions/)
* class [Document](../)
* espacio de nombres [Aspose.Words](../../document/)
* asamblea [Aspose.Words](../../../)


