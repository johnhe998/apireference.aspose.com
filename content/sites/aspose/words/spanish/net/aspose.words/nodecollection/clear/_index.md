---
title: NodeCollection.Clear
second_title: Referencia de API de Aspose.Words para .NET
description: NodeCollection método. Elimina todos los nodos de esta colección y del documento.
type: docs
weight: 40
url: /es/net/aspose.words/nodecollection/clear/
---
## NodeCollection.Clear method

Elimina todos los nodos de esta colección y del documento.

```csharp
public void Clear()
```

### Ejemplos

Muestra cómo eliminar todas las secciones de un documento.

```csharp
Document doc = new Document(MyDir + "Document.docx");

// Este documento tiene una sección con algunos nodos secundarios que contienen y muestran todo el contenido del documento.
Assert.AreEqual(1, doc.Sections.Count);
Assert.AreEqual(17, doc.Sections[0].GetChildNodes(NodeType.Any, true).Count);
Assert.AreEqual("Hello World!\r\rHello Word!\r\r\rHello World!", doc.GetText().Trim());

// Limpia la colección de secciones, lo que eliminará todos los elementos secundarios del documento.
doc.Sections.Clear();

Assert.AreEqual(0, doc.GetChildNodes(NodeType.Any, true).Count);
Assert.AreEqual(string.Empty, doc.GetText().Trim());
```

### Ver también

* class [NodeCollection](../)
* espacio de nombres [Aspose.Words](../../nodecollection/)
* asamblea [Aspose.Words](../../../)


