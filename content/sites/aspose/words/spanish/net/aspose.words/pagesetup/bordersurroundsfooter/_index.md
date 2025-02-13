---
title: PageSetup.BorderSurroundsFooter
second_title: Referencia de API de Aspose.Words para .NET
description: PageSetup propiedad. Especifica si el borde de la página incluye o excluye el pie de página.
type: docs
weight: 60
url: /es/net/aspose.words/pagesetup/bordersurroundsfooter/
---
## PageSetup.BorderSurroundsFooter property

Especifica si el borde de la página incluye o excluye el pie de página.

```csharp
public bool BorderSurroundsFooter { get; set; }
```

### Observaciones

Tenga en cuenta que cambiar esta propiedad afecta a todas las secciones del documento.

### Ejemplos

Muestra cómo aplicar un borde a la página y al encabezado/pie de página.

```csharp
Document doc = new Document();

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world! This is the main body text.");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("This is the header.");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Write("This is the footer.");
builder.MoveToDocumentEnd();

// Inserta un borde azul de doble línea.
PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.Borders.LineStyle = LineStyle.Double;
pageSetup.Borders.Color = Color.Blue;

// El objeto PageSetup de una sección tiene banderas "BorderSurroundsHeader" y "BorderSurroundsFooter" que determinan
// si un borde de página rodea el texto del cuerpo principal, también incluye el encabezado o el pie de página, respectivamente.
// Establecer el indicador "BorderSurroundsHeader" en "true" para rodear el encabezado con nuestro borde,
// y luego configure el indicador "BorderSurroundsFooter" para dejar el pie de página fuera del borde.
pageSetup.BorderSurroundsHeader = true;
pageSetup.BorderSurroundsFooter = false;

doc.Save(ArtifactsDir + "PageSetup.PageBorder.docx");
```

### Ver también

* class [PageSetup](../)
* espacio de nombres [Aspose.Words](../../pagesetup/)
* asamblea [Aspose.Words](../../../)


