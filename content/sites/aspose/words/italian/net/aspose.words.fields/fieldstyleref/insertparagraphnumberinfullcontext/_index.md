---
title: FieldStyleRef.InsertParagraphNumberInFullContext
second_title: Aspose.Words per .NET API Reference
description: FieldStyleRef proprietà. Ottiene o imposta se inserire il numero di paragrafo del paragrafo di riferimento nel contesto completo.
type: docs
weight: 30
url: /it/net/aspose.words.fields/fieldstyleref/insertparagraphnumberinfullcontext/
---
## FieldStyleRef.InsertParagraphNumberInFullContext property

Ottiene o imposta se inserire il numero di paragrafo del paragrafo di riferimento nel contesto completo.

```csharp
public bool InsertParagraphNumberInFullContext { get; set; }
```

### Esempi

Mostra come utilizzare i campi STYLEREF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea un elenco basato su un modello di elenco di Microsoft Word.
Aspose.Words.Lists.List list = doc.Lists.Add(Aspose.Words.Lists.ListTemplate.NumberDefault);

// Questo elenco generato visualizzerà "1.a )".
 // Lo spazio prima della parentesi è un carattere non delimitatore, che possiamo sopprimere.
list.ListLevels[0].NumberFormat = "\x0000.";
list.ListLevels[1].NumberFormat = "\x0001 )";

// Aggiungi testo e applica stili di paragrafo a cui faranno riferimento i campi STYLEREF.
builder.ListFormat.List = list;
builder.ListFormat.ListIndent();
builder.ParagraphFormat.Style = doc.Styles["List Paragraph"];
builder.Writeln("Item 1");
builder.ParagraphFormat.Style = doc.Styles["Quote"];
builder.Writeln("Item 2");
builder.ParagraphFormat.Style = doc.Styles["List Paragraph"];
builder.Writeln("Item 3");
builder.ListFormat.RemoveNumbers();
builder.ParagraphFormat.Style = doc.Styles["Normal"];

// Inserisci un campo STYLEREF nell'intestazione e visualizza il primo testo in stile "Paragrafo elenco" nel documento.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
FieldStyleRef field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "List Paragraph";

// Inserisci un campo STYLEREF nel piè di pagina e visualizza l'ultimo testo.
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "List Paragraph";
field.SearchFromBottom = true;

builder.MoveToDocumentEnd();

// Possiamo anche usare i campi STYLEREF per fare riferimento ai numeri degli elenchi di elenchi.
builder.Write("\nParagraph number: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumber = true;

builder.Write("\nParagraph number, relative context: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumberInRelativeContext = true;

builder.Write("\nParagraph number, full context: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumberInFullContext = true;

builder.Write("\nParagraph number, full context, non-delimiter chars suppressed: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumberInFullContext = true;
field.SuppressNonDelimiters = true;

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.STYLEREF.docx");
```

### Guarda anche

* class [FieldStyleRef](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldstyleref/)
* assemblea [Aspose.Words](../../../)


