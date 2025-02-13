---
title: FieldOptions.FieldUpdateCultureSource
second_title: Referencia de API de Aspose.Words para .NET
description: FieldOptions propiedad. Especifica qué cultura usar para formatear el resultado del campo.
type: docs
weight: 100
url: /es/net/aspose.words.fields/fieldoptions/fieldupdateculturesource/
---
## FieldOptions.FieldUpdateCultureSource property

Especifica qué cultura usar para formatear el resultado del campo.

```csharp
public FieldUpdateCultureSource FieldUpdateCultureSource { get; set; }
```

### Observaciones

De forma predeterminada, se utiliza la referencia cultural del subproceso actual.

La configuración afecta solo a los campos de fecha/hora con el cambio de formato \\@.

### Ejemplos

Muestra cómo especificar el origen de la referencia cultural utilizada para el formato de fecha durante una actualización de campo o una combinación de correspondencia.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar dos campos de combinación con la configuración regional alemana.
builder.Font.LocaleId = new CultureInfo("de-DE").LCID;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

// Establecer la referencia cultural actual en inglés estadounidense después de conservar su valor original en una variable.
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("en-US");

// Esta combinación usará la referencia cultural del subproceso actual para dar formato a la fecha, inglés estadounidense.
doc.MailMerge.Execute(new[] { "Date1" }, new object[] { new DateTime(2020, 1, 01) });

// Configure la próxima combinación para obtener su valor cultural del código de campo. El valor de esa cultura será el alemán.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.MailMerge.Execute(new[] { "Date2" }, new object[] { new DateTime(2020, 1, 01) });

// El primer resultado de la fusión contiene una fecha con formato en inglés, mientras que la segunda está en alemán.
Assert.AreEqual("Wednesday, 1 January 2020 - Mittwoch, 1 Januar 2020", doc.Range.Text.Trim());

// Restaurar la referencia cultural original del subproceso.
Thread.CurrentThread.CurrentCulture = currentCulture;
```

### Ver también

* enum [FieldUpdateCultureSource](../../fieldupdateculturesource/)
* class [FieldOptions](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldoptions/)
* asamblea [Aspose.Words](../../../)


