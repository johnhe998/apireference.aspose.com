---
title: ConditionalStyle.ClearFormatting
second_title: Referencia de API de Aspose.Words para .NET
description: ConditionalStyle método. Borra el formato de este estilo condicional.
type: docs
weight: 100
url: /es/net/aspose.words/conditionalstyle/clearformatting/
---
## ConditionalStyle.ClearFormatting method

Borra el formato de este estilo condicional.

```csharp
public void ClearFormatting()
```

### Ejemplos

Muestra cómo restablecer estilos de tabla condicionales.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("First row");
builder.EndRow();
builder.InsertCell();
builder.Write("Last row");
builder.EndTable();

TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
table.Style = tableStyle;

// Establecer el estilo de la tabla para colorear los bordes de la primera fila de la tabla en rojo.
tableStyle.ConditionalStyles.FirstRow.Borders.Color = Color.Red;

// Establecer el estilo de la tabla para colorear los bordes de la última fila de la tabla en azul.
tableStyle.ConditionalStyles.LastRow.Borders.Color = Color.Blue;

// A continuación se muestran dos formas de usar el método "ClearFormatting" para borrar los estilos condicionales.
// 1 - Limpiar los estilos condicionales para una parte específica de una tabla:
tableStyle.ConditionalStyles[0].ClearFormatting();

Assert.AreEqual(Color.Empty, tableStyle.ConditionalStyles.FirstRow.Borders.Color);

// 2 - Borrar los estilos condicionales para toda la tabla:
tableStyle.ConditionalStyles.ClearFormatting();

Assert.True(tableStyle.ConditionalStyles.All(s => s.Borders.Color == Color.Empty));
```

### Ver también

* class [ConditionalStyle](../)
* espacio de nombres [Aspose.Words](../../conditionalstyle/)
* asamblea [Aspose.Words](../../../)


