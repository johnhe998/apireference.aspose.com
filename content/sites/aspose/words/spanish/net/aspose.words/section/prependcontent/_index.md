---
title: Section.PrependContent
second_title: Referencia de API de Aspose.Words para .NET
description: Section método. Inserta una copia del contenido de la sección fuente al principio de esta sección.
type: docs
weight: 140
url: /es/net/aspose.words/section/prependcontent/
---
## Section.PrependContent method

Inserta una copia del contenido de la sección fuente al principio de esta sección.

```csharp
public void PrependContent(Section sourceSection)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| sourceSection | Section | La sección desde la que copiar el contenido. |

### Observaciones

Solo contenido de[`Body`](../body/) de la sección de origen se copia, configuración de página, encabezados y pies de página no se copian.

Los nodos se importan automáticamente si la sección de origen pertenece a un documento diferente.

No se crea ninguna nueva sección en el documento de destino.

### Ejemplos

Muestra cómo agregar el contenido de una sección a otra sección.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 3");

Section section = doc.Sections[2];

Assert.AreEqual("Section 3" + ControlChar.SectionBreak, section.GetText());

// Inserta el contenido de la primera sección al comienzo de la tercera sección.
Section sectionToPrepend = doc.Sections[0];
section.PrependContent(sectionToPrepend);

// Inserta el contenido de la segunda sección al final de la tercera sección.
Section sectionToAppend = doc.Sections[1];
section.AppendContent(sectionToAppend);

// Los métodos "PrependContent" y "AppendContent" no crearon ninguna sección nueva.
Assert.AreEqual(3, doc.Sections.Count);
Assert.AreEqual("Section 1" + ControlChar.ParagraphBreak +
                "Section 3" + ControlChar.ParagraphBreak +
                "Section 2" + ControlChar.SectionBreak, section.GetText());
```

### Ver también

* class [Section](../)
* espacio de nombres [Aspose.Words](../../section/)
* asamblea [Aspose.Words](../../../)


