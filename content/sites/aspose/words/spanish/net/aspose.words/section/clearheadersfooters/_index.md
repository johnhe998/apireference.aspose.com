---
title: Section.ClearHeadersFooters
second_title: Referencia de API de Aspose.Words para .NET
description: Section método. Borra los encabezados y pies de página de esta sección.
type: docs
weight: 100
url: /es/net/aspose.words/section/clearheadersfooters/
---
## Section.ClearHeadersFooters method

Borra los encabezados y pies de página de esta sección.

```csharp
public void ClearHeadersFooters()
```

### Observaciones

El texto de todos los encabezados y pies de página se borra, pero[`HeaderFooter`](../../headerfooter/) los objetos en sí no se eliminan.

Esto hace que los encabezados y pies de página de esta sección estén vinculados a los encabezados y pies de página de la sección anterior.

### Ejemplos

Muestra cómo borrar el contenido de todos los encabezados y pies de página en una sección.

```csharp
Document doc = new Document();

Assert.AreEqual(0, doc.FirstSection.HeadersFooters.Count);

DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Writeln("This is the primary header.");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Writeln("This is the primary footer.");

Assert.AreEqual(2, doc.FirstSection.HeadersFooters.Count);

Assert.AreEqual("This is the primary header.", doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].GetText().Trim());
Assert.AreEqual("This is the primary footer.", doc.FirstSection.HeadersFooters[HeaderFooterType.FooterPrimary].GetText().Trim());

// Vaciar todos los encabezados y pies de página de esta sección de todo su contenido.
// Los encabezados y pies de página seguirán estando presentes pero no tendrán nada que mostrar.
doc.FirstSection.ClearHeadersFooters();

Assert.AreEqual(2, doc.FirstSection.HeadersFooters.Count);

Assert.AreEqual(string.Empty, doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].GetText().Trim());
Assert.AreEqual(string.Empty, doc.FirstSection.HeadersFooters[HeaderFooterType.FooterPrimary].GetText().Trim());
```

### Ver también

* class [Section](../)
* espacio de nombres [Aspose.Words](../../section/)
* asamblea [Aspose.Words](../../../)


