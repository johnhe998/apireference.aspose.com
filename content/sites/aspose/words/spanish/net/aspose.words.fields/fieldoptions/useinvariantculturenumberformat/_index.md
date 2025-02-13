---
title: FieldOptions.UseInvariantCultureNumberFormat
second_title: Referencia de API de Aspose.Words para .NET
description: FieldOptions propiedad. Obtiene o establece el valor que indica que el formato de número se analiza utilizando la referencia cultural invariable o no
type: docs
weight: 190
url: /es/net/aspose.words.fields/fieldoptions/useinvariantculturenumberformat/
---
## FieldOptions.UseInvariantCultureNumberFormat property

Obtiene o establece el valor que indica que el formato de número se analiza utilizando la referencia cultural invariable o no

```csharp
public bool UseInvariantCultureNumberFormat { get; set; }
```

### Observaciones

Cuando esta propiedad se establece en **verdadero** , el formato de número se toma de una referencia cultural invariable.

Cuando esta propiedad se establece en **falso** el formato de número se toma de la referencia cultural del subproceso actual.

El valor predeterminado es **falso**.

### Ejemplos

Muestra cómo dar formato a los números de acuerdo con la referencia cultural invariable.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
Field field = builder.InsertField(" = 1234567,89 \\# $#,###,###.##");
field.Update();

// A veces, los campos pueden no formatear sus números correctamente bajo ciertas culturas. 
Assert.IsFalse(doc.FieldOptions.UseInvariantCultureNumberFormat);
Assert.AreEqual("$1234567,89 .     ", field.Result);

// Para solucionar esto, podríamos cambiar la cultura de todo el hilo.
// Otra forma de arreglar esto es establecer esta bandera,
// que hace que todos los campos usen la referencia cultural invariable al formatear números.
// Esta forma nos permite evitar cambiar la cultura de todo el hilo.
doc.FieldOptions.UseInvariantCultureNumberFormat = true;
field.Update();
Assert.AreEqual("$1.234.567,89", field.Result);
```

### Ver también

* class [FieldOptions](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldoptions/)
* asamblea [Aspose.Words](../../../)


