---
title: FieldSet.BookmarkName
second_title: Aspose.Words per .NET API Reference
description: FieldSet proprietà. Ottiene o imposta il nome del segnalibro.
type: docs
weight: 20
url: /it/net/aspose.words.fields/fieldset/bookmarkname/
---
## FieldSet.BookmarkName property

Ottiene o imposta il nome del segnalibro.

```csharp
public string BookmarkName { get; set; }
```

### Esempi

Mostra come creare testo con segnalibro con un campo SET e quindi visualizzarlo nel documento utilizzando un campo REF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

 // Assegna un nome al testo con segnalibro con un campo SET.
// Questo campo fa riferimento al "segnalibro" non a una struttura di segnalibri che appare all'interno del testo, ma a una variabile denominata.
FieldSet fieldSet = (FieldSet)builder.InsertField(FieldType.FieldSet, false);
fieldSet.BookmarkName = "MyBookmark";
fieldSet.BookmarkText = "Hello world!";
fieldSet.Update();

Assert.AreEqual(" SET  MyBookmark \"Hello world!\"", fieldSet.GetFieldCode());

// Fare riferimento al segnalibro per nome in un campo REF e visualizzarne il contenuto.
FieldRef fieldRef = (FieldRef)builder.InsertField(FieldType.FieldRef, true);
fieldRef.BookmarkName = "MyBookmark";
fieldRef.Update();

Assert.AreEqual(" REF  MyBookmark", fieldRef.GetFieldCode());
Assert.AreEqual("Hello world!", fieldRef.Result);

doc.Save(ArtifactsDir + "Field.SET.REF.docx");
```

### Guarda anche

* class [FieldSet](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldset/)
* assemblea [Aspose.Words](../../../)


