---
title: PageSetup.Bidi
second_title: Aspose.Words per .NET API Reference
description: PageSetup proprietà. Specifica che questa sezione contiene testo bidirezionale script complessi.
type: docs
weight: 10
url: /it/net/aspose.words/pagesetup/bidi/
---
## PageSetup.Bidi property

Specifica che questa sezione contiene testo bidirezionale (script complessi).

```csharp
public bool Bidi { get; set; }
```

### Osservazioni

Quando è vero, le colonne in questa sezione sono disposte da destra a sinistra.

### Esempi

Mostra come impostare l'ordine delle colonne di testo in una sezione.

```csharp
Document doc = new Document();

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.TextColumns.SetCount(3);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Write("Column 2.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Write("Column 3.");

// Imposta la proprietà "Bidi" su "true" per disporre le colonne a partire dal lato destro della pagina.
// L'ordine delle colonne corrisponderà alla direzione del testo da destra a sinistra.
// Imposta la proprietà "Bidi" su "false" per disporre le colonne a partire dal lato sinistro della pagina.
// L'ordine delle colonne corrisponderà alla direzione del testo da sinistra a destra.
pageSetup.Bidi = reverseColumns;

doc.Save(ArtifactsDir + "PageSetup.Bidi.docx");
```

### Guarda anche

* class [PageSetup](../)
* spazio dei nomi [Aspose.Words](../../pagesetup/)
* assemblea [Aspose.Words](../../../)


