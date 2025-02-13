---
title: FieldInclude.LockFields
second_title: Aspose.Words per .NET API Reference
description: FieldInclude proprietà. Ottiene o imposta se impedire laggiornamento dei campi nel documento incluso.
type: docs
weight: 30
url: /it/net/aspose.words.fields/fieldinclude/lockfields/
---
## FieldInclude.LockFields property

Ottiene o imposta se impedire l'aggiornamento dei campi nel documento incluso.

```csharp
public bool LockFields { get; set; }
```

### Esempi

Mostra come creare un campo INCLUDE e impostarne le proprietà.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Possiamo usare un campo INCLUDE per importare una parte di un altro documento nel file system locale.
// Il segnalibro dell'altro documento a cui facciamo riferimento con questo campo contiene questa parte importata.
FieldInclude field = (FieldInclude)builder.InsertField(FieldType.FieldInclude, true);
field.SourceFullName = MyDir + "Bookmarks.docx";
field.BookmarkName = "MyBookmark1";
field.LockFields = false;
field.TextConverter = "Microsoft Word";

Assert.True(Regex.Match(field.GetFieldCode(), " INCLUDE .* MyBookmark1 \\\\c \"Microsoft Word\"").Success);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INCLUDE.docx");
```

### Guarda anche

* class [FieldInclude](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldinclude/)
* assemblea [Aspose.Words](../../../)


