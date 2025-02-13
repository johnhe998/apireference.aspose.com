---
title: HeaderFooter.IsLinkedToPrevious
second_title: Referencia de API de Aspose.Words para .NET
description: HeaderFooter propiedad. Verdadero si este encabezado o pie de página está vinculado al encabezado o pie de página correspondiente en la sección anterior.
type: docs
weight: 40
url: /es/net/aspose.words/headerfooter/islinkedtoprevious/
---
## HeaderFooter.IsLinkedToPrevious property

Verdadero si este encabezado o pie de página está vinculado al encabezado o pie de página correspondiente en la sección anterior.

```csharp
public bool IsLinkedToPrevious { get; set; }
```

### Observaciones

El valor predeterminado es verdadero.

Tenga en cuenta que cuando su enlace es un encabezado o pie de página, su contenido se borra.

### Ejemplos

Muestra cómo vincular encabezados y pies de página entre secciones.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 3");

// Vaya a la primera sección y cree un encabezado y un pie de página. Por defecto,
// el encabezado y el pie de página solo aparecerán en las páginas de la sección que los contiene.
builder.MoveToSection(0);

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("This is the header, which will be displayed in sections 1 and 2.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Write("This is the footer, which will be displayed in sections 1, 2 and 3.");

// Podemos vincular los encabezados/pies de página de una sección a los encabezados/pies de página de la sección anterior
// para permitir que la sección de enlace muestre los encabezados/pies de página de la sección enlazada.
doc.Sections[1].HeadersFooters.LinkToPrevious(true);

// Cada sección aún tendrá sus propios objetos de encabezado/pie de página. Cuando vinculamos secciones,
// la sección de enlace mostrará el encabezado/pie de página de la sección enlazada manteniendo el suyo propio.
Assert.AreNotEqual(doc.Sections[0].HeadersFooters[0], doc.Sections[1].HeadersFooters[0]);
Assert.AreNotEqual(doc.Sections[0].HeadersFooters[0].ParentSection, doc.Sections[1].HeadersFooters[0].ParentSection);

// Vincular los encabezados/pies de página de la tercera sección a los encabezados/pies de página de la segunda sección.
// La segunda sección ya enlaza con el encabezado/pie de página de la primera sección,
// por lo que vincular a la segunda sección creará una cadena de enlaces.
// La primera, la segunda y ahora la tercera sección mostrarán los encabezados de la primera sección.
doc.Sections[2].HeadersFooters.LinkToPrevious(true);

// Podemos desvincular el encabezado/pie de página de una sección anterior pasando "falso" al llamar al método LinkToPrevious.
doc.Sections[2].HeadersFooters.LinkToPrevious(false);

// También podemos seleccionar solo un tipo específico de encabezado/pie de página para vincular usando este método.
// La tercera sección ahora tendrá el mismo pie de página que la segunda y la primera sección, pero no el encabezado.
doc.Sections[2].HeadersFooters.LinkToPrevious(HeaderFooterType.FooterPrimary, true);

// Los encabezados/pies de página de la primera sección no pueden vincularse a nada porque no hay una sección anterior.
Assert.AreEqual(2, doc.Sections[0].HeadersFooters.Count);
Assert.AreEqual(2, doc.Sections[0].HeadersFooters.Count(hf => !((HeaderFooter)hf).IsLinkedToPrevious));

// Todos los encabezados/pies de página de la segunda sección están vinculados a los encabezados/pies de página de la primera sección.
Assert.AreEqual(6, doc.Sections[1].HeadersFooters.Count);
Assert.AreEqual(6, doc.Sections[1].HeadersFooters.Count(hf => ((HeaderFooter)hf).IsLinkedToPrevious));

// En la tercera sección, solo el pie de página está vinculado al pie de página de la primera sección a través de la segunda sección.
Assert.AreEqual(6, doc.Sections[2].HeadersFooters.Count);
Assert.AreEqual(5, doc.Sections[2].HeadersFooters.Count(hf => !((HeaderFooter)hf).IsLinkedToPrevious));
Assert.True(doc.Sections[2].HeadersFooters[3].IsLinkedToPrevious);

doc.Save(ArtifactsDir + "HeaderFooter.Link.docx");
```

### Ver también

* class [HeaderFooter](../)
* espacio de nombres [Aspose.Words](../../headerfooter/)
* asamblea [Aspose.Words](../../../)


