---
title: FieldInclude.BookmarkName
second_title: Referencia de API de Aspose.Words para .NET
description: FieldInclude propiedad. Obtiene o establece el nombre del marcador en el documento a incluir.
type: docs
weight: 20
url: /es/net/aspose.words.fields/fieldinclude/bookmarkname/
---
## FieldInclude.BookmarkName property

Obtiene o establece el nombre del marcador en el documento a incluir.

```csharp
public string BookmarkName { get; set; }
```

### Ejemplos

Muestra cómo crear un campo INCLUDE y establecer sus propiedades.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Podemos usar un campo INCLUDE para importar una parte de otro documento en el sistema de archivos local.
// El marcador del otro documento al que hacemos referencia con este campo contiene esta parte importada.
FieldInclude field = (FieldInclude)builder.InsertField(FieldType.FieldInclude, true);
field.SourceFullName = MyDir + "Bookmarks.docx";
field.BookmarkName = "MyBookmark1";
field.LockFields = false;
field.TextConverter = "Microsoft Word";

Assert.True(Regex.Match(field.GetFieldCode(), " INCLUDE .* MyBookmark1 \\\\c \"Microsoft Word\"").Success);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INCLUDE.docx");
```

### Ver también

* class [FieldInclude](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldinclude/)
* asamblea [Aspose.Words](../../../)


