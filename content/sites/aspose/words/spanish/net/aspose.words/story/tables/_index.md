---
title: Story.Tables
second_title: Referencia de API de Aspose.Words para .NET
description: Story propiedad. Obtiene una colección de tablas que son elementos secundarios inmediatos de la historia.
type: docs
weight: 50
url: /es/net/aspose.words/story/tables/
---
## Story.Tables property

Obtiene una colección de tablas que son elementos secundarios inmediatos de la historia.

```csharp
public TableCollection Tables { get; }
```

### Ejemplos

Muestra cómo eliminar la primera y la última fila de todas las tablas de un documento.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

TableCollection tables = doc.FirstSection.Body.Tables;

Assert.AreEqual(5, tables[0].Rows.Count);
Assert.AreEqual(4, tables[1].Rows.Count);

foreach (Table table in tables.OfType<Table>())
{
    table.FirstRow?.Remove();
    table.LastRow?.Remove();
}

Assert.AreEqual(3, tables[0].Rows.Count);
Assert.AreEqual(2, tables[1].Rows.Count);
```

### Ver también

* class [TableCollection](../../../aspose.words.tables/tablecollection/)
* class [Story](../)
* espacio de nombres [Aspose.Words](../../story/)
* asamblea [Aspose.Words](../../../)


