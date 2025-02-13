---
title: FieldFileSize.IsInKilobytes
second_title: Referencia de API de Aspose.Words para .NET
description: FieldFileSize propiedad. Obtiene o establece si mostrar el tamaño del archivo en kilobytes.
type: docs
weight: 20
url: /es/net/aspose.words.fields/fieldfilesize/isinkilobytes/
---
## FieldFileSize.IsInKilobytes property

Obtiene o establece si mostrar el tamaño del archivo en kilobytes.

```csharp
public bool IsInKilobytes { get; set; }
```

### Ejemplos

Muestra cómo mostrar el tamaño de archivo de un documento con un campo TAMAÑO DE ARCHIVO.

```csharp
Document doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(18105, doc.BuiltInDocumentProperties.Bytes);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.InsertParagraph();

// Abajo hay tres unidades de medida diferentes
// con qué campos FILESIZE pueden mostrar el tamaño del archivo del documento.
// 1 - bytes:
FieldFileSize field = (FieldFileSize)builder.InsertField(FieldType.FieldFileSize, true);
field.Update();

Assert.AreEqual(" FILESIZE ", field.GetFieldCode());
Assert.AreEqual("18105", field.Result);

// 2 - Kilobytes:
builder.InsertParagraph();
field = (FieldFileSize)builder.InsertField(FieldType.FieldFileSize, true);
field.IsInKilobytes = true;
field.Update();

Assert.AreEqual(" FILESIZE  \\k", field.GetFieldCode());
Assert.AreEqual("18", field.Result);

// 3 - Megabytes:
builder.InsertParagraph();
field = (FieldFileSize)builder.InsertField(FieldType.FieldFileSize, true);
field.IsInMegabytes = true;
field.Update();

Assert.AreEqual(" FILESIZE  \\m", field.GetFieldCode());
Assert.AreEqual("0", field.Result);

// Para actualizar los valores de estos campos mientras edita en Microsoft Word,
// primero debemos guardar los cambios y luego actualizar manualmente estos campos.
doc.Save(ArtifactsDir + "Field.FILESIZE.docx");
```

### Ver también

* class [FieldFileSize](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldfilesize/)
* asamblea [Aspose.Words](../../../)


