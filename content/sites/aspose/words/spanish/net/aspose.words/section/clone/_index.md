---
title: Section.Clone
second_title: Referencia de API de Aspose.Words para .NET
description: Section método. Crea un duplicado de esta sección.
type: docs
weight: 110
url: /es/net/aspose.words/section/clone/
---
## Section.Clone method

Crea un duplicado de esta sección.

```csharp
public Section Clone()
```

### Ejemplos

Muestra cómo agregar y eliminar secciones en un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");

Assert.AreEqual("Section 1\x000cSection 2", doc.GetText().Trim());

// Eliminar la primera sección del documento.
doc.Sections.RemoveAt(0);

Assert.AreEqual("Section 2", doc.GetText().Trim());

// Agregue una copia de lo que ahora es la primera sección al final del documento.
int lastSectionIdx = doc.Sections.Count - 1;
Section newSection = doc.Sections[lastSectionIdx].Clone();
doc.Sections.Add(newSection);

Assert.AreEqual("Section 2\x000cSection 2", doc.GetText().Trim());
```

### Ver también

* class [Section](../)
* espacio de nombres [Aspose.Words](../../section/)
* asamblea [Aspose.Words](../../../)


