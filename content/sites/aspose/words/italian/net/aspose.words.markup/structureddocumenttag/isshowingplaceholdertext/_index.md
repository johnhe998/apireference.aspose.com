---
title: StructuredDocumentTag.IsShowingPlaceholderText
second_title: Aspose.Words per .NET API Reference
description: StructuredDocumentTag proprietà. Specifica se il contenuto di questo SDT deve essere interpretato per contenere testo segnaposto al contrario dei normali contenuti di testo allinterno dellSDT.
type: docs
weight: 150
url: /it/net/aspose.words.markup/structureddocumenttag/isshowingplaceholdertext/
---
## StructuredDocumentTag.IsShowingPlaceholderText property

Specifica se il contenuto di questo **SDT** deve essere interpretato per contenere testo segnaposto (al contrario dei normali contenuti di testo all'interno dell'SDT).

se impostato su true, questo stato verrà ripristinato (mostrando il testo segnaposto) all'apertura di questo documento.

```csharp
public bool IsShowingPlaceholderText { get; set; }
```

### Esempi

Mostra come utilizzare il contenuto di un blocco predefinito come testo segnaposto personalizzato per un tag di documento strutturato.

```csharp
Document doc = new Document();

// Inserisce un tag di documento strutturato in testo normale del tipo "Testo semplice", che fungerà da casella di testo.
// I contenuti che visualizzerà per impostazione predefinita sono "Fai clic qui per inserire il testo". richiesta.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline);

// Possiamo ottenere il tag per visualizzare il contenuto di un blocco predefinito invece del testo predefinito.
// Innanzitutto, aggiungi un blocco predefinito con contenuti al documento del glossario.
GlossaryDocument glossaryDoc = doc.GlossaryDocument;

BuildingBlock substituteBlock = new BuildingBlock(glossaryDoc);
substituteBlock.Name = "Custom Placeholder";
substituteBlock.AppendChild(new Section(glossaryDoc));
substituteBlock.FirstSection.AppendChild(new Body(glossaryDoc));
substituteBlock.FirstSection.Body.AppendParagraph("Custom placeholder text.");

glossaryDoc.AppendChild(substituteBlock);

// Quindi, utilizza la proprietà "PlaceholderName" del tag del documento strutturato per fare riferimento a quel blocco predefinito in base al nome.
tag.PlaceholderName = "Custom Placeholder";

// Se "PlaceholderName" fa riferimento a un blocco esistente nel documento di glossario del documento principale,
// saremo in grado di verificare il blocco costitutivo tramite la proprietà "Segnaposto".
Assert.AreEqual(substituteBlock, tag.Placeholder);

// Imposta la proprietà "IsShowingPlaceholderText" su "true" per trattare il
// Contenuti correnti del tag del documento strutturato come testo segnaposto.
// Ciò significa che facendo clic sulla casella di testo in Microsoft Word si evidenzierà immediatamente tutto il contenuto del tag.
// Imposta la proprietà "IsShowingPlaceholderText" su "false" per ottenere il file
// tag del documento strutturato per trattare il suo contenuto come testo che un utente ha già inserito.
// Facendo clic su questo testo in Microsoft Word, il cursore lampeggiante verrà posizionato nella posizione in cui si è fatto clic.
tag.IsShowingPlaceholderText = isShowingPlaceholderText;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(tag);

doc.Save(ArtifactsDir + "StructuredDocumentTag.PlaceholderBuildingBlock.docx");
```

### Guarda anche

* class [StructuredDocumentTag](../)
* spazio dei nomi [Aspose.Words.Markup](../../structureddocumenttag/)
* assemblea [Aspose.Words](../../../)


