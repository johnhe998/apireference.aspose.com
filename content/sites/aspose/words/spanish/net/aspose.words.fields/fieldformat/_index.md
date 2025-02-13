---
title: Class FieldFormat
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Fields.FieldFormat clase. Proporciona acceso escrito al formato numérico de fecha y hora y general del campo.
type: docs
weight: 1790
url: /es/net/aspose.words.fields/fieldformat/
---
## FieldFormat class

Proporciona acceso escrito al formato numérico, de fecha y hora y general del campo.

```csharp
public class FieldFormat
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [DateTimeFormat](../../aspose.words.fields/fieldformat/datetimeformat/) { get; set; } | Obtiene o establece un formato que se aplica a un resultado de campo de fecha y hora. Corresponde al \@ switch. |
| [GeneralFormats](../../aspose.words.fields/fieldformat/generalformats/) { get; } | Obtiene una colección de formatos generales que se aplican a un resultado numérico, de texto o de cualquier campo. Corresponde a los \* modificadores. |
| [NumericFormat](../../aspose.words.fields/fieldformat/numericformat/) { get; set; } | Obtiene o establece un formato que se aplica a un resultado de campo numérico. Corresponde al \# switch. |

### Ejemplos

Muestra cómo dar formato a los resultados de los campos.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Use un generador de documentos para insertar un campo que muestre un resultado sin formato aplicado.
Field field = builder.InsertField("= 2 + 3");

Assert.AreEqual("= 2 + 3", field.GetFieldCode());
Assert.AreEqual("5", field.Result);

// Podemos aplicar un formato al resultado de un campo usando las propiedades del campo.
// A continuación se muestran tres tipos de formatos que podemos aplicar al resultado de un campo.
// 1 - Formato numérico:
FieldFormat format = field.Format;
format.NumericFormat = "$###.00";
field.Update();

Assert.AreEqual("= 2 + 3 \\# $###.00", field.GetFieldCode());
Assert.AreEqual("$  5.00", field.Result);

// 2 - Formato de fecha/hora:
field = builder.InsertField("DATE");
format = field.Format;
format.DateTimeFormat = "dddd, MMMM dd, yyyy";
field.Update();

Assert.AreEqual("DATE \\@ \"dddd, MMMM dd, yyyy\"", field.GetFieldCode());
Console.WriteLine($"Today's date, in {format.DateTimeFormat} format:\n\t{field.Result}");

// 3 - Formato general:
field = builder.InsertField("= 25 + 33");
format = field.Format;
format.GeneralFormats.Add(GeneralFormat.LowercaseRoman);
format.GeneralFormats.Add(GeneralFormat.Upper);
field.Update();

int index = 0;
using (IEnumerator<GeneralFormat> generalFormatEnumerator = format.GeneralFormats.GetEnumerator())
    while (generalFormatEnumerator.MoveNext())
        Console.WriteLine($"General format index {index++}: {generalFormatEnumerator.Current}");

Assert.AreEqual("= 25 + 33 \\* roman \\* Upper", field.GetFieldCode());
Assert.AreEqual("LVIII", field.Result);
Assert.AreEqual(2, format.GeneralFormats.Count);
Assert.AreEqual(GeneralFormat.LowercaseRoman, format.GeneralFormats[0]);

// Podemos eliminar nuestros formatos para revertir el resultado del campo a su forma original.
format.GeneralFormats.Remove(GeneralFormat.LowercaseRoman);
format.GeneralFormats.RemoveAt(0);
Assert.AreEqual(0, format.GeneralFormats.Count);
field.Update();

Assert.AreEqual("= 25 + 33  ", field.GetFieldCode());
Assert.AreEqual("58", field.Result);
Assert.AreEqual(0, format.GeneralFormats.Count);
```

### Ver también

* espacio de nombres [Aspose.Words.Fields](../../aspose.words.fields/)
* asamblea [Aspose.Words](../../)


