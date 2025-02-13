---
title: Shape.HasSmartArt
second_title: Referencia de API de Aspose.Words para .NET
description: Shape propiedad. Devuelve verdadero si esta Forma tiene un objeto SmartArt.
type: docs
weight: 90
url: /es/net/aspose.words.drawing/shape/hassmartart/
---
## Shape.HasSmartArt property

Devuelve verdadero si esta Forma tiene un objeto SmartArt.

```csharp
public bool HasSmartArt { get; }
```

### Ejemplos

Muestra cómo contar el número de formas en un documento con objetos SmartArt.

```csharp
Document doc = new Document(MyDir + "SmartArt.docx");

int numberOfSmartArtShapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmartArt);

Assert.AreEqual(2, numberOfSmartArtShapes);
```

### Ver también

* class [Shape](../)
* espacio de nombres [Aspose.Words.Drawing](../../shape/)
* asamblea [Aspose.Words](../../../)


