---
title: FieldSubject.Text
second_title: Referencia de API de Aspose.Words para .NET
description: FieldSubject propiedad. Obtiene o establece el texto del asunto.
type: docs
weight: 20
url: /es/net/aspose.words.fields/fieldsubject/text/
---
## FieldSubject.Text property

Obtiene o establece el texto del asunto.

```csharp
public string Text { get; set; }
```

### Ejemplos

Muestra cómo utilizar el campo ASUNTO.

```csharp
Document doc = new Document();

// Establecer un valor para la propiedad integrada "Asunto" del documento.
doc.BuiltInDocumentProperties.Subject = "My subject";

// Cree un campo SUBJECT para mostrar el valor de esa propiedad integrada.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldSubject field = (FieldSubject)builder.InsertField(FieldType.FieldSubject, true);
field.Update();

Assert.AreEqual(" SUBJECT ", field.GetFieldCode());
Assert.AreEqual("My subject", field.Result);

// Si asignamos el valor de la propiedad Texto del campo ASUNTO y lo actualizamos, el campo
// sobrescribe el valor actual de la propiedad integrada "Asunto" con el valor de su propiedad Texto,
// y luego mostrar el nuevo valor.
field.Text = "My new subject";
field.Update();

Assert.AreEqual(" SUBJECT  \"My new subject\"", field.GetFieldCode());
Assert.AreEqual("My new subject", field.Result);

Assert.AreEqual("My new subject", doc.BuiltInDocumentProperties.Subject);

doc.Save(ArtifactsDir + "Field.SUBJECT.docx");
```

### Ver también

* class [FieldSubject](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldsubject/)
* asamblea [Aspose.Words](../../../)


