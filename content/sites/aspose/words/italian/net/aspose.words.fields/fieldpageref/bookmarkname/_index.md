---
title: FieldPageRef.BookmarkName
second_title: Aspose.Words per .NET API Reference
description: FieldPageRef proprietà. Ottiene o imposta il nome del segnalibro.
type: docs
weight: 20
url: /it/net/aspose.words.fields/fieldpageref/bookmarkname/
---
## FieldPageRef.BookmarkName property

Ottiene o imposta il nome del segnalibro.

```csharp
public string BookmarkName { get; set; }
```

### Esempi

Mostra per inserire i campi PAGEREF per visualizzare la posizione relativa dei segnalibri.

```csharp
public void FieldPageRef()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    InsertAndNameBookmark(builder, "MyBookmark1");

    // Inserisce un campo PAGEREF che mostra in quale pagina si trova un segnalibro.
    // Imposta il flag InsertHyperlink per fare in modo che il campo funzioni anche come collegamento cliccabile al segnalibro.
    Assert.AreEqual(" PAGEREF  MyBookmark3 \\h", 
        InsertFieldPageRef(builder, "MyBookmark3", true, false, "Hyperlink to Bookmark3, on page: ").GetFieldCode());

    // Possiamo usare il flag \p per visualizzare il campo PAGEREF
    // la posizione del segnalibro rispetto alla posizione del campo.
    // Bookmark1 è sulla stessa pagina e sopra questo campo, quindi il risultato visualizzato di questo campo sarà "sopra".
    Assert.AreEqual(" PAGEREF  MyBookmark1 \\h \\p", 
        InsertFieldPageRef(builder, "MyBookmark1", true, true, "Bookmark1 is ").GetFieldCode());

    // Bookmark2 sarà sulla stessa pagina e sotto questo campo, quindi il risultato visualizzato di questo campo sarà "sotto".
    Assert.AreEqual(" PAGEREF  MyBookmark2 \\h \\p", 
        InsertFieldPageRef(builder, "MyBookmark2", true, true, "Bookmark2 is ").GetFieldCode());

    // Bookmark3 sarà su una pagina diversa, quindi il campo visualizzerà "on page 2".
    Assert.AreEqual(" PAGEREF  MyBookmark3 \\h \\p", 
        InsertFieldPageRef(builder, "MyBookmark3", true, true, "Bookmark3 is ").GetFieldCode());

    InsertAndNameBookmark(builder, "MyBookmark2");
    builder.InsertBreak(BreakType.PageBreak);
    InsertAndNameBookmark(builder, "MyBookmark3");

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.PAGEREF.docx");

/// <summary>
/// Utilizza un generatore di documenti per inserire un campo PAGEREF e ne imposta le proprietà.
/// </summary>
private static FieldPageRef InsertFieldPageRef(DocumentBuilder builder, string bookmarkName, bool insertHyperlink, bool insertRelativePosition, string textBefore)
{
    builder.Write(textBefore);

    FieldPageRef field = (FieldPageRef)builder.InsertField(FieldType.FieldPageRef, true);
    field.BookmarkName = bookmarkName;
    field.InsertHyperlink = insertHyperlink;
    field.InsertRelativePosition = insertRelativePosition;
    builder.Writeln();

    return field;
}

/// <summary>
/// Utilizza un generatore di documenti per inserire un segnalibro con nome.
/// </summary>
private static void InsertAndNameBookmark(DocumentBuilder builder, string bookmarkName)
{
    builder.StartBookmark(bookmarkName);
    builder.Writeln($"Contents of bookmark \"{bookmarkName}\".");
    builder.EndBookmark(bookmarkName);
}
```

### Guarda anche

* class [FieldPageRef](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldpageref/)
* assemblea [Aspose.Words](../../../)


