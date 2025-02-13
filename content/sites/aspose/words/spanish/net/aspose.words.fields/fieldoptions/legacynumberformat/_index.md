---
title: FieldOptions.LegacyNumberFormat
second_title: Referencia de API de Aspose.Words para .NET
description: FieldOptions propiedad. Obtiene o establece el valor que indica si el formato de número heredado anterior a AW 13.10 para los campos está habilitado o no.
type: docs
weight: 140
url: /es/net/aspose.words.fields/fieldoptions/legacynumberformat/
---
## FieldOptions.LegacyNumberFormat property

Obtiene o establece el valor que indica si el formato de número heredado (anterior a AW 13.10) para los campos está habilitado o no.

```csharp
public bool LegacyNumberFormat { get; set; }
```

### Observaciones

Cuando esta propiedad se establece en **verdadero**, el símbolo de plantilla "#" funcionó como en .net: Reemplaza el signo de libra con el dígito correspondiente si hay uno presente; de lo contrario, no aparece ningún símbolo en la cadena de resultados.

Cuando esta propiedad se establece en **falso**, el símbolo de plantilla "#" funciona como MS Word: Este elemento de formato especifica los lugares numéricos necesarios para mostrar en el resultado. Si el resultado no incluye un dígito en ese lugar, MS Word muestra un espacio. Por ejemplo, { = 9 + 6 \# $### } muestra $ 15.

El valor predeterminado es **falso**.

### Ejemplos

Muestra cómo habilitar el formato de número heredado para los campos.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Field field = builder.InsertField("= 2 + 3 \\# $##");

Assert.AreEqual("$ 5", field.Result);

doc.FieldOptions.LegacyNumberFormat = true;
field.Update();

Assert.AreEqual("$5", field.Result);
```

### Ver también

* class [FieldOptions](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldoptions/)
* asamblea [Aspose.Words](../../../)


