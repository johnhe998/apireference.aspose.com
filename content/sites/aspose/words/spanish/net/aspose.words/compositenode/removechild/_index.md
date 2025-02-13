---
title: CompositeNode.RemoveChild
second_title: Referencia de API de Aspose.Words para .NET
description: CompositeNode método. Elimina el nodo secundario especificado.
type: docs
weight: 180
url: /es/net/aspose.words/compositenode/removechild/
---
## CompositeNode.RemoveChild method

Elimina el nodo secundario especificado.

```csharp
public Node RemoveChild(Node oldChild)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| oldChild | Node | El nodo a eliminar. |

### Valor_devuelto

El nodo eliminado.

### Observaciones

El padre de oldChild se establece en nulo después de eliminar el nodo.

### Ejemplos

Muestra cómo usar los métodos Node y CompositeNode para eliminar una sección antes de la última sección del documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1 text.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2 text.");

// Ambas secciones son hermanas entre sí.
Section lastSection = (Section)doc.LastChild;
Section firstSection = (Section)lastSection.PreviousSibling;

// Eliminar una sección en función de su relación de hermanos con otra sección.
if (lastSection.PreviousSibling != null)
    doc.RemoveChild(firstSection);

// La sección que eliminamos fue la primera, dejando el documento solo con la segunda.
Assert.AreEqual("Section 2 text.", doc.GetText().Trim());
```

### Ver también

* class [Node](../../node/)
* class [CompositeNode](../)
* espacio de nombres [Aspose.Words](../../compositenode/)
* asamblea [Aspose.Words](../../../)


