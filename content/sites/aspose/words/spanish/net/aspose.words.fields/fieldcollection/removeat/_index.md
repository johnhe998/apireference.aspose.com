---
title: FieldCollection.RemoveAt
second_title: Referencia de API de Aspose.Words para .NET
description: FieldCollection método. Elimina un campo en el índice especificado de esta colección y del documento.
type: docs
weight: 60
url: /es/net/aspose.words.fields/fieldcollection/removeat/
---
## FieldCollection.RemoveAt method

Elimina un campo en el índice especificado de esta colección y del documento.

```csharp
public void RemoveAt(int index)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| index | Int32 | Un índice de la colección. |

### Ejemplos

Muestra cómo eliminar campos de una colección de campos.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" DATE \\@ \"dddd, d MMMM yyyy\" ");
builder.InsertField(" TIME ");
builder.InsertField(" REVNUM ");
builder.InsertField(" AUTHOR  \"John Doe\" ");
builder.InsertField(" SUBJECT \"My Subject\" ");
builder.InsertField(" QUOTE \"Hello world!\" ");
doc.UpdateFields();

FieldCollection fields = doc.Range.Fields;

Assert.AreEqual(6, fields.Count);

// A continuación se muestran cuatro formas de eliminar campos de una colección de campos.
// 1 - Obtener un campo para eliminarlo:
fields[0].Remove();
Assert.AreEqual(5, fields.Count);

// 2 - Obtener la colección para eliminar un campo que le pasamos a su método de eliminación:
Field lastField = fields[3];
fields.Remove(lastField);
Assert.AreEqual(4, fields.Count);

// 3 - Eliminar un campo de una colección en un índice:
fields.RemoveAt(2);
Assert.AreEqual(3, fields.Count);

// 4 - Elimina todos los campos de la colección a la vez:
fields.Clear();
Assert.AreEqual(0, fields.Count);
```

### Ver también

* class [FieldCollection](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldcollection/)
* asamblea [Aspose.Words](../../../)


