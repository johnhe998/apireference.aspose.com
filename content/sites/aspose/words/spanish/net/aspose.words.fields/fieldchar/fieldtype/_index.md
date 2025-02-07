---
title: FieldChar.FieldType
second_title: Referencia de API de Aspose.Words para .NET
description: FieldChar propiedad. Devuelve el tipo del campo.
type: docs
weight: 10
url: /es/net/aspose.words.fields/fieldchar/fieldtype/
---
## FieldChar.FieldType property

Devuelve el tipo del campo.

```csharp
public FieldType FieldType { get; }
```

### Ejemplos

Muestra cómo trabajar con un nodo FieldStart.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldDate field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.Format.DateTimeFormat = "dddd, MMMM dd, yyyy";
field.Update();

FieldChar fieldStart = field.Start;

Assert.AreEqual(FieldType.FieldDate, fieldStart.FieldType);
Assert.AreEqual(false, fieldStart.IsDirty);
Assert.AreEqual(false, fieldStart.IsLocked);

// Recuperar el objeto de fachada que representa el campo en el documento.
field = (FieldDate)fieldStart.GetField();

Assert.AreEqual(false, field.IsLocked);
Assert.AreEqual(" DATE  \\@ \"dddd, MMMM dd, yyyy\"", field.GetFieldCode());

// Actualizar el campo para mostrar la fecha actual.
field.Update();
```

### Ver también

* enum [FieldType](../../fieldtype/)
* class [FieldChar](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldchar/)
* asamblea [Aspose.Words](../../../)


