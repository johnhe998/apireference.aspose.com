---
title: PreferredWidth.Type
second_title: Referencia de API de Aspose.Words para .NET
description: PreferredWidth propiedad. Obtiene la unidad de medida utilizada para este valor de ancho preferido.
type: docs
weight: 40
url: /es/net/aspose.words.tables/preferredwidth/type/
---
## PreferredWidth.Type property

Obtiene la unidad de medida utilizada para este valor de ancho preferido.

```csharp
public PreferredWidthType Type { get; }
```

### Ejemplos

Muestra cómo verificar el tipo de ancho preferido y el valor de una celda de tabla.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

Table table = doc.FirstSection.Body.Tables[0];
Cell firstCell = table.FirstRow.FirstCell;

Assert.AreEqual(PreferredWidthType.Percent, firstCell.CellFormat.PreferredWidth.Type);
Assert.AreEqual(11.16d, firstCell.CellFormat.PreferredWidth.Value);
```

### Ver también

* enum [PreferredWidthType](../../preferredwidthtype/)
* class [PreferredWidth](../)
* espacio de nombres [Aspose.Words.Tables](../../preferredwidth/)
* asamblea [Aspose.Words](../../../)


