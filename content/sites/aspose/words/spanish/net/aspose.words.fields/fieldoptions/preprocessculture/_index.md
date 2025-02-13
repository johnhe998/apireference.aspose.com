---
title: FieldOptions.PreProcessCulture
second_title: Referencia de API de Aspose.Words para .NET
description: FieldOptions propiedad. Obtiene o establece la referencia cultural para preprocesar valores de campo.
type: docs
weight: 150
url: /es/net/aspose.words.fields/fieldoptions/preprocessculture/
---
## FieldOptions.PreProcessCulture property

Obtiene o establece la referencia cultural para preprocesar valores de campo.

```csharp
public CultureInfo PreProcessCulture { get; set; }
```

### Observaciones

Actualmente esta propiedad solo afecta el valor de la[`FieldDocProperty`](../../fielddocproperty/) campo.

El valor predeterminado es **nulo** . Cuando esta propiedad se establece en **nulo** , la[`FieldDocProperty`](../../fielddocproperty/) el valor del campo es preprocesado con la cultura controlada por el[`FieldUpdateCultureSource`](../fieldupdateculturesource/) propiedad.

### Ejemplos

Muestra cómo establecer la referencia cultural de preprocesamiento.

```csharp
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// Establecer la cultura según la cual algunos campos formatearán sus valores mostrados.
doc.FieldOptions.PreProcessCulture = new CultureInfo("de-DE");

Field field = builder.InsertField(" DOCPROPERTY CreateTime");

// El campo DOCPROPERTY mostrará su resultado formateado de acuerdo con la cultura del preproceso
// lo hemos puesto en alemán. El campo mostrará la fecha/hora usando el formato "dd.mm.yyyy hh:mm".
Assert.IsTrue(Regex.Match(field.Result, @"\d{2}[.]\d{2}[.]\d{4} \d{2}[:]\d{2}").Success);

doc.FieldOptions.PreProcessCulture = CultureInfo.InvariantCulture;
field.Update();

// Después de cambiar a la cultura invariable, el campo DOCPROPERTY usará el formato "mm/dd/yyyy hh:mm".
Assert.IsTrue(Regex.Match(field.Result, @"\d{2}[/]\d{2}[/]\d{4} \d{2}[:]\d{2}").Success);
```

### Ver también

* class [FieldOptions](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldoptions/)
* asamblea [Aspose.Words](../../../)


