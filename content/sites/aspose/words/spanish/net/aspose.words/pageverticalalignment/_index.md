---
title: Enum PageVerticalAlignment
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.PageVerticalAlignment enumeración. Especifica la justificación vertical del texto en cada página.
type: docs
weight: 4130
url: /es/net/aspose.words/pageverticalalignment/
---
## PageVerticalAlignment enumeration

Especifica la justificación vertical del texto en cada página.

```csharp
public enum PageVerticalAlignment
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| Bottom | `3` | El texto está alineado en la parte inferior de la página. |
| Center | `1` | El texto está alineado en el centro de la página. |
| Justify | `2` | El texto se extiende para llenar la página. |
| Top | `0` | El texto está alineado en la parte superior de la página. |

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

* class [PageSetup](../pagesetup/)
* property [VerticalAlignment](../pagesetup/verticalalignment/)
* espacio de nombres [Aspose.Words](../../aspose.words/)
* asamblea [Aspose.Words](../../)


