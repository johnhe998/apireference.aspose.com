---
title: FieldOptions.DefaultDocumentAuthor
second_title: Referencia de API de Aspose.Words para .NET
description: FieldOptions propiedad. Obtiene o establece el nombre del autor del documento predeterminado. Si el nombre del autor ya está especificado en las propiedades integradas del documento esta opción no se considera.
type: docs
weight: 60
url: /es/net/aspose.words.fields/fieldoptions/defaultdocumentauthor/
---
## FieldOptions.DefaultDocumentAuthor property

Obtiene o establece el nombre del autor del documento predeterminado. Si el nombre del autor ya está especificado en las propiedades integradas del documento, esta opción no se considera.

```csharp
public string DefaultDocumentAuthor { get; set; }
```

### Ejemplos

Muestra cómo usar un campo AUTOR para mostrar el nombre del creador de un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Los campos AUTOR obtienen sus resultados de la propiedad de documento incorporada llamada "Autor".
// Si creamos y guardamos un documento en Microsoft Word,
// tendrá nuestro nombre de usuario en esa propiedad.
// Sin embargo, si creamos un documento programáticamente usando Aspose.Words,
  // la propiedad "Autor", por defecto, será una cadena vacía.
Assert.AreEqual(string.Empty, doc.BuiltInDocumentProperties.Author);

// Establecer un nombre de autor de respaldo para los campos AUTHOR para usar
// si la propiedad "Autor" contiene una cadena vacía.
doc.FieldOptions.DefaultDocumentAuthor = "Joe Bloggs";

builder.Write("This document was created by ");
FieldAuthor field = (FieldAuthor)builder.InsertField(FieldType.FieldAuthor, true);
field.Update();

Assert.AreEqual(" AUTHOR ", field.GetFieldCode());
Assert.AreEqual("Joe Bloggs", field.Result);

// Actualizar un campo AUTOR que contiene un valor
// aplicará ese valor a la propiedad integrada "Autor".
Assert.AreEqual("Joe Bloggs", doc.BuiltInDocumentProperties.Author);

// Al cambiar esta propiedad y luego actualizar el campo AUTOR, se aplicará este valor al campo.
doc.BuiltInDocumentProperties.Author = "John Doe";      
field.Update();

Assert.AreEqual(" AUTHOR ", field.GetFieldCode());
Assert.AreEqual("John Doe", field.Result);

// Si actualizamos un campo AUTOR después de cambiar su propiedad "Nombre",
// entonces el campo mostrará el nuevo nombre y aplicará el nuevo nombre a la propiedad integrada.
field.AuthorName = "Jane Doe";
field.Update();

Assert.AreEqual(" AUTHOR  \"Jane Doe\"", field.GetFieldCode());
Assert.AreEqual("Jane Doe", field.Result);

// Los campos AUTOR no afectan la propiedad DefaultDocumentAuthor.
Assert.AreEqual("Jane Doe", doc.BuiltInDocumentProperties.Author);
Assert.AreEqual("Joe Bloggs", doc.FieldOptions.DefaultDocumentAuthor);

doc.Save(ArtifactsDir + "Field.AUTHOR.docx");
```

### Ver también

* class [FieldOptions](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldoptions/)
* asamblea [Aspose.Words](../../../)


