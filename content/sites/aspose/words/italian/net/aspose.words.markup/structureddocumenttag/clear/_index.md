---
title: StructuredDocumentTag.Clear
second_title: Aspose.Words per .NET API Reference
description: StructuredDocumentTag metodo. Cancella il contenuto di questo tag del documento strutturato e visualizza un segnaposto se è definito.
type: docs
weight: 330
url: /it/net/aspose.words.markup/structureddocumenttag/clear/
---
## StructuredDocumentTag.Clear method

Cancella il contenuto di questo tag del documento strutturato e visualizza un segnaposto se è definito.

```csharp
public void Clear()
```

### Osservazioni

Non è possibile cancellare il contenuto di un tag di documento strutturato se ha delle revisioni.

Se questo tag del documento strutturato è mappato su XML personalizzato (con l'utilizzo di[`XmlMapping`](../xmlmapping/) ), il nodo XML di riferimento viene cancellato.

### Esempi

Mostra come eliminare i contenuti degli elementi di tag del documento strutturato.

```csharp
Document doc = new Document();

// Crea un tag documento strutturato in testo normale, quindi aggiungilo al documento.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(tag);

// Questo tag del documento strutturato, che ha la forma di una casella di testo, mostra già il testo segnaposto.
Assert.AreEqual("Click here to enter text.", tag.GetText().Trim());
Assert.True(tag.IsShowingPlaceholderText);

// Crea un building block con contenuto di testo.
GlossaryDocument glossaryDoc = doc.GlossaryDocument;
BuildingBlock substituteBlock = new BuildingBlock(glossaryDoc);
substituteBlock.Name = "My placeholder";
substituteBlock.AppendChild(new Section(glossaryDoc));
substituteBlock.FirstSection.EnsureMinimum();
substituteBlock.FirstSection.Body.FirstParagraph.AppendChild(new Run(glossaryDoc, "Custom placeholder text."));
glossaryDoc.AppendChild(substituteBlock);

// Imposta la proprietà "PlaceholderName" del tag del documento strutturato sul nome del nostro blocco predefinito per ottenere
// il tag del documento strutturato per visualizzare il contenuto del blocco predefinito al posto del testo predefinito originale.
tag.PlaceholderName = "My placeholder";

Assert.AreEqual("Custom placeholder text.", tag.GetText().Trim());
Assert.True(tag.IsShowingPlaceholderText);

// Modifica il testo del tag del documento strutturato e nasconde il testo segnaposto.
Run run = (Run)tag.GetChild(NodeType.Run, 0, true);
run.Text = "New text.";
tag.IsShowingPlaceholderText = false;

Assert.AreEqual("New text.", tag.GetText().Trim());

// Usa il metodo "Cancella" per cancellare il contenuto di questo tag del documento strutturato e visualizzare nuovamente il segnaposto.
tag.Clear();

Assert.True(tag.IsShowingPlaceholderText);
Assert.AreEqual("Custom placeholder text.", tag.GetText().Trim());
```

### Guarda anche

* class [StructuredDocumentTag](../)
* spazio dei nomi [Aspose.Words.Markup](../../structureddocumenttag/)
* assemblea [Aspose.Words](../../../)


