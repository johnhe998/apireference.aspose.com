---
title: FieldIndex.BookmarkName
second_title: Referencia de API de Aspose.Words para .NET
description: FieldIndex propiedad. Obtiene o establece el nombre del marcador que marca la parte del documento utilizada para generar el índice.
type: docs
weight: 20
url: /es/net/aspose.words.fields/fieldindex/bookmarkname/
---
## FieldIndex.BookmarkName property

Obtiene o establece el nombre del marcador que marca la parte del documento utilizada para generar el índice.

```csharp
public string BookmarkName { get; set; }
```

### Ejemplos

Muestra cómo crear un campo ÍNDICE y luego usar campos XE para llenarlo con entradas.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Cree un campo ÍNDICE que mostrará una entrada para cada campo XE encontrado en el documento.
// Cada entrada mostrará el valor de la propiedad Texto del campo XE en el lado izquierdo
// y la página que contiene el campo XE a la derecha.
// Si los campos XE tienen el mismo valor en su propiedad "Texto",
// el campo ÍNDICE los agrupará en una sola entrada.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// Configure el campo ÍNDICE solo para mostrar los campos XE que están dentro de los límites
// de un marcador llamado "MainBookmark", y cuyas propiedades "EntryType" tienen un valor de "A".
// Para los campos INDEX y XE, la propiedad "EntryType" solo usa el primer carácter de su valor de cadena.
index.BookmarkName = "MainBookmark";
index.EntryType = "A";

Assert.AreEqual(" INDEX  \\b MainBookmark \\f A", index.GetFieldCode());

// En una nueva página, comience el marcador con un nombre que coincida con el valor
// de la propiedad "BookmarkName" del campo ÍNDICE.
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("MainBookmark");

// El campo ÍNDICE recogerá esta entrada porque está dentro del marcador,
// y su tipo de entrada también coincide con el tipo de entrada del campo ÍNDICE.
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 1";
indexEntry.EntryType = "A";

Assert.AreEqual(" XE  \"Index entry 1\" \\f A", indexEntry.GetFieldCode());

// Inserte un campo XE que no aparecerá en el ÍNDICE porque los tipos de entrada no coinciden.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 2";
indexEntry.EntryType = "B";

// Termina el marcador e inserta un campo XE después.
// Es del mismo tipo que el campo ÍNDICE, pero no aparecerá
// ya que está fuera de los límites del marcador.
builder.EndBookmark("MainBookmark");
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 3";
indexEntry.EntryType = "A";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Filtering.docx");
```

### Ver también

* class [FieldIndex](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldindex/)
* asamblea [Aspose.Words](../../../)


