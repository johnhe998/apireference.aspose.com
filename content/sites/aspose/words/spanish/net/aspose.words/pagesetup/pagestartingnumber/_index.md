---
title: PageSetup.PageStartingNumber
second_title: Referencia de API de Aspose.Words para .NET
description: PageSetup propiedad. Obtiene o establece el número de página inicial de la sección.
type: docs
weight: 320
url: /es/net/aspose.words/pagesetup/pagestartingnumber/
---
## PageSetup.PageStartingNumber property

Obtiene o establece el número de página inicial de la sección.

```csharp
public int PageStartingNumber { get; set; }
```

### Observaciones

El[`RestartPageNumbering`](../restartpagenumbering/) propiedad, si se establece en **falso** , anulará the  **PáginaInicioNúmero** propiedad para que la numeración de páginas pueda continuar desde la sección anterior.

### Ejemplos

Muestra cómo configurar la numeración de páginas en una sección.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1, page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Section 1, page 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Section 1, page 3.");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Writeln("Section 2, page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Section 2, page 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Section 2, page 3.");

// Mover el generador de documentos al encabezado principal de la primera sección,
// que se mostrará en todas las páginas de esa sección.
builder.MoveToSection(0);
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Inserta un campo de PÁGINA, que mostrará el número de la página actual.
builder.Write("Page ");
builder.InsertField("PAGE", "");

// Configure la sección para que el recuento de páginas que muestran los campos de PÁGINA comience desde 5.
// Además, configure todos los campos de PÁGINA para mostrar sus números de página usando números romanos en mayúsculas.
PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.RestartPageNumbering = true;
pageSetup.PageStartingNumber = 5;
pageSetup.PageNumberStyle = NumberStyle.UppercaseRoman;

// Cree otro encabezado principal para la segunda sección, con otro campo de PÁGINA.
builder.MoveToSection(1);
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write(" - ");
builder.InsertField("PAGE", "");
builder.Write(" - ");

// Configure la sección para que el recuento de páginas que muestran los campos de PÁGINA comience desde 10.
// Además, configure todos los campos de PÁGINA para mostrar sus números de página usando números arábigos.
pageSetup = doc.Sections[1].PageSetup;
pageSetup.PageStartingNumber = 10;
pageSetup.RestartPageNumbering = true;
pageSetup.PageNumberStyle = NumberStyle.Arabic;

doc.Save(ArtifactsDir + "PageSetup.PageNumbering.docx");
```

### Ver también

* class [PageSetup](../)
* espacio de nombres [Aspose.Words](../../pagesetup/)
* asamblea [Aspose.Words](../../../)


