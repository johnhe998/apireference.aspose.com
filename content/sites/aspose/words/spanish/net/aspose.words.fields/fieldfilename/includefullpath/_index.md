---
title: FieldFileName.IncludeFullPath
second_title: Referencia de API de Aspose.Words para .NET
description: FieldFileName propiedad. Obtiene o establece si se debe incluir el nombre completo de la ruta del archivo.
type: docs
weight: 20
url: /es/net/aspose.words.fields/fieldfilename/includefullpath/
---
## FieldFileName.IncludeFullPath property

Obtiene o establece si se debe incluir el nombre completo de la ruta del archivo.

```csharp
public bool IncludeFullPath { get; set; }
```

### Ejemplos

Muestra cómo utilizar FieldOptions para anular el valor predeterminado del campo FILENAME.

```csharp
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToDocumentEnd();
builder.Writeln();

// Este campo NOMBRE DE ARCHIVO mostrará el nombre del archivo del sistema local del documento que cargamos.
FieldFileName field = (FieldFileName)builder.InsertField(FieldType.FieldFileName, true);
field.Update();

Assert.AreEqual(" FILENAME ", field.GetFieldCode());
Assert.AreEqual("Document.docx", field.Result);

builder.Writeln();

// De forma predeterminada, el campo NOMBRE DE ARCHIVO muestra el nombre del archivo, pero no la ruta completa del sistema de archivos local.
// Podemos establecer un indicador para que muestre la ruta completa del archivo.
field = (FieldFileName)builder.InsertField(FieldType.FieldFileName, true);
field.IncludeFullPath = true;
field.Update();

Assert.AreEqual(MyDir + "Document.docx", field.Result);

// También podemos establecer un valor para esta propiedad para
// anula el valor que muestra el campo NOMBRE DE ARCHIVO.
doc.FieldOptions.FileName = "FieldOptions.FILENAME.docx";
field.Update();

Assert.AreEqual(" FILENAME  \\p", field.GetFieldCode());
Assert.AreEqual("FieldOptions.FILENAME.docx", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + doc.FieldOptions.FileName);
```

### Ver también

* class [FieldFileName](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldfilename/)
* asamblea [Aspose.Words](../../../)


