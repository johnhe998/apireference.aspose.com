---
title: FormField.Type
second_title: Referencia de API de Aspose.Words para .NET
description: FormField propiedad. Devuelve el tipo de campo de formulario.
type: docs
weight: 220
url: /es/net/aspose.words.fields/formfield/type/
---
## FormField.Type property

Devuelve el tipo de campo de formulario.

```csharp
public FieldType Type { get; }
```

### Ejemplos

Muestra cómo insertar un cuadro combinado.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please select a fruit: ");

// Inserte un cuadro combinado que permitirá al usuario elegir una opción de una colección de cadenas.
FormField comboBox = builder.InsertComboBox("MyComboBox", new[] { "Apple", "Banana", "Cherry" }, 0);

Assert.AreEqual("MyComboBox", comboBox.Name);
Assert.AreEqual(FieldType.FieldFormDropDown, comboBox.Type);
Assert.AreEqual("Apple", comboBox.Result);

// El campo del formulario aparecerá en forma de una etiqueta html "seleccionar".
doc.Save(ArtifactsDir + "FormFields.Create.html");
```

### Ver también

* enum [FieldType](../../fieldtype/)
* class [FormField](../)
* espacio de nombres [Aspose.Words.Fields](../../formfield/)
* asamblea [Aspose.Words](../../../)


