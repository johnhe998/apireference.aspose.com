---
title: FieldInclude.TextConverter
second_title: Aspose.Words per .NET API Reference
description: FieldInclude proprietà. Ottiene o imposta il nome del convertitore di testo per il formato del file incluso.
type: docs
weight: 50
url: /it/net/aspose.words.fields/fieldinclude/textconverter/
---
## FieldInclude.TextConverter property

Ottiene o imposta il nome del convertitore di testo per il formato del file incluso.

```csharp
public string TextConverter { get; set; }
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


