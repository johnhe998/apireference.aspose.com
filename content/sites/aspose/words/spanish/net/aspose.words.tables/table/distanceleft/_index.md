---
title: Table.DistanceLeft
second_title: Referencia de API de Aspose.Words para .NET
description: Table propiedad. Obtiene la distancia entre la izquierda de la tabla y el texto circundante en puntos.
type: docs
weight: 130
url: /es/net/aspose.words.tables/table/distanceleft/
---
## Table.DistanceLeft property

Obtiene la distancia entre la izquierda de la tabla y el texto circundante, en puntos.

```csharp
public double DistanceLeft { get; }
```

### Ejemplos

Muestra las operaciones de distancia mínima entre los límites de la tabla y el texto.

```csharp
Document doc = new Document(MyDir + "Table wrapped by text.docx");

Table table = doc.FirstSection.Body.Tables[0];

Assert.AreEqual(25.9d, table.DistanceTop);
Assert.AreEqual(25.9d, table.DistanceBottom);
Assert.AreEqual(17.3d, table.DistanceLeft);
Assert.AreEqual(17.3d, table.DistanceRight);
```

### Ver también

* class [Table](../)
* espacio de nombres [Aspose.Words.Tables](../../table/)
* asamblea [Aspose.Words](../../../)


