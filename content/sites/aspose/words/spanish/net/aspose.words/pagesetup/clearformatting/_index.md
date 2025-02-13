---
title: PageSetup.ClearFormatting
second_title: Referencia de API de Aspose.Words para .NET
description: PageSetup método. Restablece la configuración de página al tamaño de papel los márgenes y la orientación predeterminados.
type: docs
weight: 450
url: /es/net/aspose.words/pagesetup/clearformatting/
---
## PageSetup.ClearFormatting method

Restablece la configuración de página al tamaño de papel, los márgenes y la orientación predeterminados.

```csharp
public void ClearFormatting()
```

### Ejemplos

Muestra cómo aplicar y revertir la configuración de configuración de página a las secciones de un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Modifique las propiedades de configuración de la página para la sección actual del constructor y agregue texto.
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.VerticalAlignment = PageVerticalAlignment.Center;
builder.Writeln("This is the first section, which landscape oriented with vertically centered text.");

// Si comenzamos una nueva sección usando un generador de documentos,
// heredará las propiedades de configuración de la página actual del constructor.
builder.InsertBreak(BreakType.SectionBreakNewPage);

Assert.AreEqual(Orientation.Landscape, doc.Sections[1].PageSetup.Orientation);
Assert.AreEqual(PageVerticalAlignment.Center, doc.Sections[1].PageSetup.VerticalAlignment);

// Podemos revertir sus propiedades de configuración de página a sus valores predeterminados usando el método "ClearFormatting".
builder.PageSetup.ClearFormatting();

Assert.AreEqual(Orientation.Portrait, doc.Sections[1].PageSetup.Orientation);
Assert.AreEqual(PageVerticalAlignment.Top, doc.Sections[1].PageSetup.VerticalAlignment);

builder.Writeln("This is the second section, which is in default Letter paper size, portrait orientation and top alignment.");

doc.Save(ArtifactsDir + "PageSetup.ClearFormatting.docx");
```

### Ver también

* class [PageSetup](../)
* espacio de nombres [Aspose.Words](../../pagesetup/)
* asamblea [Aspose.Words](../../../)


