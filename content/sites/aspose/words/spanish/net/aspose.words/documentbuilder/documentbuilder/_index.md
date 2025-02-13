---
title: DocumentBuilder.DocumentBuilder
second_title: Referencia de API de Aspose.Words para .NET
description: DocumentBuilder constructor. Inicializa una nueva instancia de esta clase.
type: docs
weight: 10
url: /es/net/aspose.words/documentbuilder/documentbuilder/
---
## DocumentBuilder() {#constructor}

Inicializa una nueva instancia de esta clase.

```csharp
public DocumentBuilder()
```

### Observaciones

Crea un nuevo **Creador de documentos** objeto y lo adjunta a un nuevo[`Document`](../document/) objeto.

### Ejemplos

Muestra cómo insertar texto con formato utilizando DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Especifique el formato de fuente, luego agregue texto.
Aspose.Words.Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Courier New";
font.Underline = Underline.Dash;

builder.Write("Hello world!");
```

### Ver también

* class [DocumentBuilder](../)
* espacio de nombres [Aspose.Words](../../documentbuilder/)
* asamblea [Aspose.Words](../../../)

---

## DocumentBuilder(Document) {#constructor_1}

Inicializa una nueva instancia de esta clase.

```csharp
public DocumentBuilder(Document doc)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| doc | Document | El objeto Documento al que adjuntar. |

### Observaciones

Crea un nuevo **Creador de documentos** objeto, se adjunta al especificado[`Document`](../document/) objeto. El cursor se posiciona al principio del documento.

### Ejemplos

Muestra cómo crear encabezados y pies de página en un documento usando DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Especificar que queremos encabezados y pies de página diferentes para las primeras páginas, pares e impares.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Cree los encabezados, luego agregue tres páginas al documento para mostrar cada tipo de encabezado.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page3");

doc.Save(ArtifactsDir + "DocumentBuilder.HeadersAndFooters.docx");
```

Muestra cómo insertar una tabla de contenido (TOC) en un documento utilizando estilos de título como entradas.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta una tabla de contenido para la primera página del documento.
// Configure la tabla para recoger párrafos con encabezados de niveles 1 a 3.
// Además, configure sus entradas para que sean hipervínculos que nos llevarán
// a la ubicación del encabezado cuando se hace clic con el botón izquierdo en Microsoft Word.
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
builder.InsertBreak(BreakType.PageBreak);

// Complete la tabla de contenido agregando párrafos con estilos de encabezado.
// Cada encabezado con un nivel entre 1 y 3 creará una entrada en la tabla.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading4;
builder.Writeln("Heading 3.1.3.1");
builder.Writeln("Heading 3.1.3.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");

// Una tabla de contenido es un campo de un tipo que debe actualizarse para mostrar un resultado actualizado.
doc.UpdateFields();
doc.Save(ArtifactsDir + "DocumentBuilder.InsertToc.docx");
```

### Ver también

* class [Document](../../document/)
* class [DocumentBuilder](../)
* espacio de nombres [Aspose.Words](../../documentbuilder/)
* asamblea [Aspose.Words](../../../)


