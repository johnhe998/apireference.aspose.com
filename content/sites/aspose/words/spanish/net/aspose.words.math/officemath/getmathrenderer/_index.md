---
title: OfficeMath.GetMathRenderer
second_title: Referencia de API de Aspose.Words para .NET
description: OfficeMath método. Crea y devuelve un objeto que se puede usar para convertir esta ecuación en una imagen.
type: docs
weight: 80
url: /es/net/aspose.words.math/officemath/getmathrenderer/
---
## OfficeMath.GetMathRenderer method

Crea y devuelve un objeto que se puede usar para convertir esta ecuación en una imagen.

```csharp
public OfficeMathRenderer GetMathRenderer()
```

### Valor_devuelto

El objeto renderizador para esta ecuación.

### Observaciones

Este método simplemente invoca el[`OfficeMathRenderer`](../../../aspose.words.rendering/officemathrenderer/)constructor y pasa este objeto como parámetro.

### Ejemplos

Muestra cómo representar un objeto de Office Math en un archivo de imagen en el sistema de archivos local.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath math = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);

// Crear un objeto "ImageSaveOptions" para pasar al método "Guardar" del renderizador de nodos para modificar
// cómo convierte el nodo OfficeMath en una imagen.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png);

// Establezca la propiedad "Escala" en 5 para representar el objeto cinco veces su tamaño original.
saveOptions.Scale = 5;

math.GetMathRenderer().Save(ArtifactsDir + "Shape.RenderOfficeMath.png", saveOptions);
```

### Ver también

* class [OfficeMathRenderer](../../../aspose.words.rendering/officemathrenderer/)
* class [OfficeMath](../)
* espacio de nombres [Aspose.Words.Math](../../officemath/)
* asamblea [Aspose.Words](../../../)


