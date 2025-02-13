---
title: Field.LocaleId
second_title: Referencia de API de Aspose.Words para .NET
description: Field propiedad. Obtiene o establece el LCID del campo.
type: docs
weight: 60
url: /es/net/aspose.words.fields/field/localeid/
---
## Field.LocaleId property

Obtiene o establece el LCID del campo.

```csharp
public int LocaleId { get; set; }
```

### Ejemplos

Muestra cómo insertar un campo y trabajar con su configuración regional.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserte un campo de FECHA y luego imprima la fecha que se mostrará.
// La cultura actual de su hilo determina el formato de la fecha.
Field field = builder.InsertField(@"DATE");
Console.WriteLine($"Today's date, as displayed in the \"{CultureInfo.CurrentCulture.EnglishName}\" culture: {field.Result}");

Assert.AreEqual(1033, field.LocaleId);
// Cambiar la cultura de nuestro hilo afectará el resultado del campo FECHA.
// Otra forma de hacer que el campo FECHA muestre una fecha en una cultura diferente es usar su propiedad LocaleId.
// Esta forma nos permite evitar cambiar la cultura del hilo para conseguir este efecto.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
CultureInfo de = new CultureInfo("de-DE");
field.LocaleId = de.LCID;
field.Update();

Console.WriteLine($"Today's date, as displayed according to the \"{CultureInfo.GetCultureInfo(field.LocaleId).EnglishName}\" culture: {field.Result}");
```

### Ver también

* class [Field](../)
* espacio de nombres [Aspose.Words.Fields](../../field/)
* asamblea [Aspose.Words](../../../)


