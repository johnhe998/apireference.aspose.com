---
title: FieldDatabase.Query
second_title: Referencia de API de Aspose.Words para .NET
description: FieldDatabase propiedad. Obtiene o establece un conjunto de instrucciones SQL que consultan la base de datos.
type: docs
weight: 90
url: /es/net/aspose.words.fields/fielddatabase/query/
---
## FieldDatabase.Query property

Obtiene o establece un conjunto de instrucciones SQL que consultan la base de datos.

```csharp
public string Query { get; set; }
```

### Ejemplos

Muestra cómo extraer datos de una base de datos e insertarlos como un campo en un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Este campo BASE DE DATOS ejecutará una consulta en una base de datos y mostrará el resultado en una tabla.
FieldDatabase field = (FieldDatabase)builder.InsertField(FieldType.FieldDatabase, true);
field.FileName = MyDir + @"Database\Northwind.mdb";
field.Connection = "DSN=MS Access Databases";
field.Query = "SELECT * FROM [Products]";

Assert.AreEqual($" DATABASE  \\d \"{DatabaseDir.Replace("\\", "\\\\") + "Northwind.mdb"}\" \\c \"DSN=MS Access Databases\" \\s \"SELECT * FROM [Products]\"", 
    field.GetFieldCode());

// Inserte otro campo de BASE DE DATOS con una consulta más compleja que clasifique todos los productos en orden descendente por ventas brutas.
field = (FieldDatabase)builder.InsertField(FieldType.FieldDatabase, true);
field.FileName = MyDir + @"Database\Northwind.mdb";
field.Connection = "DSN=MS Access Databases";
field.Query =
    "SELECT [Products].ProductName, FORMAT(SUM([Order Details].UnitPrice * (1 - [Order Details].Discount) * [Order Details].Quantity), 'Currency') AS GrossSales " +
    "FROM([Products] " +
    "LEFT JOIN[Order Details] ON[Products].[ProductID] = [Order Details].[ProductID]) " +
    "GROUP BY[Products].ProductName " +
    "ORDER BY SUM([Order Details].UnitPrice* (1 - [Order Details].Discount) * [Order Details].Quantity) DESC";

// Estas propiedades tienen la misma función que las cláusulas LIMIT y TOP.
// Configurarlos para mostrar solo las filas 1 a 10 del resultado de la consulta en la tabla del campo.
field.FirstRecord = "1";
field.LastRecord = "10";

// Esta propiedad es el índice del formato que queremos usar para nuestra tabla. La lista de formatos de tabla se encuentra en el menú "Autoformato de tabla..."
// que aparece cuando creamos un campo BASE DE DATOS en Microsoft Word. El índice #10 corresponde al formato "Colorful 3".
field.TableFormat = "10";

// La propiedad FormatAttribute es una representación de cadena de un número entero que almacena varias banderas.
// Podemos aplicar patrialmente el formato al que apunta la propiedad TableFormat configurando diferentes banderas en esta propiedad.
// El número que usamos es la suma de una combinación de valores correspondientes a diferentes aspectos del estilo de la tabla.
// 63 representa 1 (bordes) + 2 (sombreado) + 4 (fuente) + 8 (color) + 16 (ajuste automático) + 32 (filas de encabezado).
field.FormatAttributes = "63";
field.InsertHeadings = true;
field.InsertOnceOnMailMerge = true;

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.DATABASE.docx");
```

### Ver también

* class [FieldDatabase](../)
* espacio de nombres [Aspose.Words.Fields](../../fielddatabase/)
* asamblea [Aspose.Words](../../../)


