---
title: OutlineOptions.CreateMissingOutlineLevels
second_title: Referencia de API de Aspose.Words para .NET
description: OutlineOptions propiedad. Obtiene o establece un valor que determina si se crean o no los niveles de esquema que faltan cuando el documento se exporta .
type: docs
weight: 30
url: /es/net/aspose.words.saving/outlineoptions/createmissingoutlinelevels/
---
## OutlineOptions.CreateMissingOutlineLevels property

Obtiene o establece un valor que determina si se crean o no los niveles de esquema que faltan cuando el documento se exporta .

El valor predeterminado para esta propiedad es **falso**.

```csharp
public bool CreateMissingOutlineLevels { get; set; }
```

### Ejemplos

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

* class [OutlineOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../outlineoptions/)
* asamblea [Aspose.Words](../../../)


