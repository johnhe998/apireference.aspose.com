---
title: FieldListNum.StartingNumber
second_title: Referencia de API de Aspose.Words para .NET
description: FieldListNum propiedad. Obtiene o establece el valor inicial de este campo.
type: docs
weight: 50
url: /es/net/aspose.words.fields/fieldlistnum/startingnumber/
---
## FieldListNum.StartingNumber property

Obtiene o establece el valor inicial de este campo.

```csharp
public string StartingNumber { get; set; }
```

### Ejemplos

Muestra cómo numerar párrafos con campos LISTNUM.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Los campos LISTNUM muestran un número que se incrementa en cada campo LISTNUM.
// Estos campos también tienen una variedad de opciones que nos permiten usarlos para emular listas numeradas.
FieldListNum field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);

// Las listas comienzan a contar en 1 de forma predeterminada, pero podemos establecer este número en un valor diferente, como 0.
// Este campo mostrará "0)".
field.StartingNumber = "0";
builder.Writeln("Paragraph 1");

Assert.AreEqual(" LISTNUM  \\s 0", field.GetFieldCode());

  // Los campos LISTNUM mantienen recuentos separados para cada nivel de lista.
// Insertar un campo LISTNUM en el mismo párrafo que otro campo LISTNUM
// aumenta el nivel de la lista en lugar del conteo.
// El siguiente campo continuará con el conteo que comenzamos arriba y mostrará un valor de "1" en el nivel 1 de la lista.
builder.InsertField(FieldType.FieldListNum, true);

// Este campo iniciará un conteo en el nivel 2 de la lista. Mostrará un valor de "1".
builder.InsertField(FieldType.FieldListNum, true);

// Este campo iniciará un conteo en el nivel 3 de la lista. Mostrará un valor de "1".
// Los diferentes niveles de lista tienen un formato diferente,
// por lo que estos campos combinados mostrarán un valor de "1)a)i)".
builder.InsertField(FieldType.FieldListNum, true);
builder.Writeln("Paragraph 2");

// El próximo campo LISTNUM que insertemos continuará el conteo a nivel de lista
// que el campo LISTNUM anterior estaba activado.
// Podemos usar la propiedad "ListLevel" para saltar a un nivel de lista diferente.
// Si este campo LISTNUM permaneciera en el nivel 3 de la lista, mostraría "ii)",
// pero, dado que lo hemos movido al nivel 2 de la lista, continúa contando en ese nivel y muestra "b)".
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.ListLevel = "2";
builder.Writeln("Paragraph 3");

Assert.AreEqual(" LISTNUM  \\l 2", field.GetFieldCode());

// Podemos establecer la propiedad ListName para que el campo emule un tipo de campo AUTONUM diferente.
// "NumberDefault" emula AUTONUM, "OutlineDefault" emula AUTONUMOUT,
// y "LegalDefault" emula los campos AUTONUMLGL.
// El nombre de la lista "OutlineDefault" con 1 como número inicial hará que se muestre "I".
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.StartingNumber = "1";
field.ListName = "OutlineDefault";
builder.Writeln("Paragraph 4");

Assert.IsTrue(field.HasListName);
Assert.AreEqual(" LISTNUM  OutlineDefault \\s 1", field.GetFieldCode());

// ListName no se transfiere del campo anterior, por lo que deberemos configurarlo para cada nuevo campo.
// Este campo continúa la cuenta con el nombre de lista diferente y muestra "II".
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.ListName = "OutlineDefault";
builder.Writeln("Paragraph 5");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.LISTNUM.docx");
```

### Ver también

* class [FieldListNum](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldlistnum/)
* asamblea [Aspose.Words](../../../)


