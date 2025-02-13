---
title: Field.DisplayResult
second_title: Referencia de API de Aspose.Words para .NET
description: Field propiedad. Obtiene el texto que representa el resultado del campo mostrado.
type: docs
weight: 10
url: /es/net/aspose.words.fields/field/displayresult/
---
## Field.DisplayResult property

Obtiene el texto que representa el resultado del campo mostrado.

```csharp
public string DisplayResult { get; }
```

### Observaciones

El[`UpdateListLabels`](../../../aspose.words/document/updatelistlabels/) se debe llamar al método para obtener el valor correcto para the [`FieldListNum`](../../fieldlistnum/) ,[`FieldAutoNum`](../../fieldautonum/) ,[`FieldAutoNumOut`](../../fieldautonumout/) y[`FieldAutoNumLgl`](../../fieldautonumlgl/) campos.

### Ejemplos

Muestra cómo obtener el texto real que muestra un campo en el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("This document was written by ");
FieldAuthor fieldAuthor = (FieldAuthor)builder.InsertField(FieldType.FieldAuthor, true);
fieldAuthor.AuthorName = "John Doe";

// Podemos usar la propiedad DisplayResult para verificar qué texto exacto
// un campo se mostraría en su lugar en el documento.
Assert.AreEqual(string.Empty, fieldAuthor.DisplayResult);

  // Los campos no mantienen valores de resultados precisos en tiempo real.
// Para asegurarnos de que nuestros campos muestren resultados precisos en cualquier momento,
// como justo antes de una operación de guardado, necesitamos actualizarlos manualmente.
fieldAuthor.Update();

Assert.AreEqual("John Doe", fieldAuthor.DisplayResult);

doc.Save(ArtifactsDir + "Field.DisplayResult.docx");
```

### Ver también

* class [Field](../)
* espacio de nombres [Aspose.Words.Fields](../../field/)
* asamblea [Aspose.Words](../../../)


