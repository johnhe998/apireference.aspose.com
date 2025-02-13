---
title: PdfSaveOptions.OutlineOptions
second_title: Referencia de API de Aspose.Words para .NET
description: PdfSaveOptions propiedad. Permite especificar opciones de contorno.
type: docs
weight: 210
url: /es/net/aspose.words.saving/pdfsaveoptions/outlineoptions/
---
## PdfSaveOptions.OutlineOptions property

Permite especificar opciones de contorno.

```csharp
public OutlineOptions OutlineOptions { get; }
```

### Observaciones

Se pueden crear esquemas a partir de encabezados y marcadores.

Para los encabezados, el nivel del esquema está determinado por el nivel del encabezado.

Es posible establecer el nivel de encabezado máximo que se incluirá en los contornos o deshabilitar los contornos de encabezado en absoluto.

Para los marcadores, el nivel de esquema se puede configurar en las opciones como un valor predeterminado para todos los marcadores o como valores individuales para marcadores particulares.

Además, los contornos se pueden exportar a formato XPS utilizando el mismo`OutlineOptions` clase.

### Ejemplos

Muestra cómo limitar el nivel de los encabezados que aparecerán en el esquema de un documento PDF guardado.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar encabezados que puedan servir como entradas de TOC de los niveles 1, 2 y luego 3.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 1.2.1");
builder.Writeln("Heading 1.2.2");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.SaveFormat = SaveFormat.Pdf;

// El documento PDF de salida contendrá un esquema, que es una tabla de contenido que enumera los encabezados en el cuerpo del documento.
// Al hacer clic en una entrada de este esquema, nos llevará a la ubicación de su respectivo encabezado.
// Establezca la propiedad "HeadingsOutlineLevels" en "2" para excluir todos los encabezados cuyos niveles estén por encima de 2 del esquema.
// Los dos últimos encabezados que hemos insertado arriba no aparecerán.
saveOptions.OutlineOptions.HeadingsOutlineLevels = 2;

doc.Save(ArtifactsDir + "PdfSaveOptions.HeadingsOutlineLevels.pdf", saveOptions);
```

Muestra cómo trabajar con niveles de esquema que no contienen títulos correspondientes al guardar un documento PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar encabezados que puedan servir como entradas de TOC de los niveles 1 y 5.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading5;

builder.Writeln("Heading 1.1.1.1.1");
builder.Writeln("Heading 1.1.1.1.2");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// El documento PDF de salida contendrá un esquema, que es una tabla de contenido que enumera los encabezados en el cuerpo del documento.
// Al hacer clic en una entrada de este esquema, nos llevará a la ubicación de su respectivo encabezado.
// Establezca la propiedad "HeadingsOutlineLevels" en "5" para incluir todos los encabezados de los niveles 5 e inferiores en el esquema.
saveOptions.OutlineOptions.HeadingsOutlineLevels = 5;

  // Este documento contiene encabezados de niveles 1 y 5, y no contiene encabezados de niveles 2, 3 y 4.
// El documento PDF de salida tratará los niveles de esquema 2, 3 y 4 como "faltantes".
// Establezca la propiedad "CreateMissingOutlineLevels" en "true" para incluir todos los niveles faltantes en el esquema,
// dejando las entradas de esquema en blanco ya que no hay encabezados utilizables.
// Establezca la propiedad "CreateMissingOutlineLevels" en "false" para ignorar los niveles de esquema faltantes,
// y trate los encabezados del nivel 5 del esquema como nivel 2.
saveOptions.OutlineOptions.CreateMissingOutlineLevels = createMissingOutlineLevels;

doc.Save(ArtifactsDir + "PdfSaveOptions.CreateMissingOutlineLevels.pdf", saveOptions);
```

### Ver también

* class [OutlineOptions](../../outlineoptions/)
* class [PdfSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../pdfsaveoptions/)
* asamblea [Aspose.Words](../../../)


