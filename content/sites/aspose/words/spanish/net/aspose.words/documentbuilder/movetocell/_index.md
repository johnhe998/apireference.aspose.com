---
title: DocumentBuilder.MoveToCell
second_title: Referencia de API de Aspose.Words para .NET
description: DocumentBuilder método. Mueve el cursor a una celda de la tabla en la sección actual.
type: docs
weight: 480
url: /es/net/aspose.words/documentbuilder/movetocell/
---
## DocumentBuilder.MoveToCell method

Mueve el cursor a una celda de la tabla en la sección actual.

```csharp
public void MoveToCell(int tableIndex, int rowIndex, int columnIndex, int characterIndex)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| tableIndex | Int32 | El índice de la tabla a la que se va a mover. |
| rowIndex | Int32 | El índice de la fila en la tabla. |
| columnIndex | Int32 | El índice de la columna en la tabla. |
| characterIndex | Int32 | El índice del carácter dentro de la celda. Un valor negativo le permite especificar una posición desde el final de la celda. Use -1 para moverse al final de la celda. |

### Observaciones

La navegación se realiza dentro de la historia actual de la sección actual.

Para los parámetros de índice, cuando el índice es mayor o igual a 0, especifica un índice from comenzando con 0 siendo el primer elemento. Cuando el índice es menor que 0, especificó un índice from el final con -1 como último elemento.

### Ejemplos

Muestra cómo mover el cursor de un generador de documentos a una celda de una tabla.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea una tabla vacía de 2x2.
builder.StartTable();
builder.InsertCell();
builder.InsertCell();
builder.EndRow();
builder.InsertCell();
builder.InsertCell();
builder.EndTable();

// Porque hemos terminado la tabla con el método EndTable,
// el cursor del generador de documentos está actualmente fuera de la tabla.
// Este cursor tiene la misma función que el cursor de texto parpadeante de Microsoft Word.
// También se puede mover a una ubicación diferente en el documento utilizando los métodos MoveTo del constructor.
// Podemos mover el cursor de regreso dentro de la tabla a una celda específica.
builder.MoveToCell(0, 1, 1, 0);
builder.Write("Column 2, cell 2.");

doc.Save(ArtifactsDir + "DocumentBuilder.MoveToCell.docx");
```

### Ver también

* class [DocumentBuilder](../)
* espacio de nombres [Aspose.Words](../../documentbuilder/)
* asamblea [Aspose.Words](../../../)


