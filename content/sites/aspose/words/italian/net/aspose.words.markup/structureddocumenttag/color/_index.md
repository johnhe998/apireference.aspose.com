---
title: StructuredDocumentTag.Color
second_title: Aspose.Words per .NET API Reference
description: StructuredDocumentTag proprietà. Ottiene o imposta il colore del tag del documento strutturato.
type: docs
weight: 70
url: /it/net/aspose.words.markup/structureddocumenttag/color/
---
## StructuredDocumentTag.Color property

Ottiene o imposta il colore del tag del documento strutturato.

```csharp
public Color Color { get; set; }
```

### Esempi

Mostra come creare un tag di documento strutturato in una casella di testo normale e modificarne l'aspetto.

```csharp
Document doc = new Document();

// Crea un tag di documento strutturato che conterrà testo normale.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline);

// Imposta il titolo e il colore della cornice che appare quando passi il mouse sopra il tag del documento strutturato in Microsoft Word.
tag.Title = "My plain text";
tag.Color = Color.Magenta;

// Imposta un tag per questo tag del documento strutturato, che è ottenibile
// come elemento XML denominato "tag", con la stringa sottostante nel suo attributo "@val".
tag.Tag = "MyPlainTextSDT";

// Ogni tag di documento strutturato ha un ID univoco casuale.
Assert.That(tag.Id, Is.Positive);

// Imposta il carattere per il testo all'interno del tag del documento strutturato.
tag.ContentsFont.Name = "Arial";

// Imposta il carattere per il testo alla fine del tag del documento strutturato.
// Qualsiasi testo digitato nel corpo del documento dopo essere uscito dal tag con i tasti freccia utilizzerà questo tipo di carattere.
tag.EndCharacterFont.Name = "Arial Black";

// Per impostazione predefinita, questo è falso e premere invio mentre si è all'interno di un tag di documento strutturato non fa nulla.
// Se impostato su true, il nostro tag di documento strutturato può avere più righe.

// Imposta la proprietà "Multiline" su "false" per consentire solo il contenuto
// di questo tag del documento strutturato su una singola riga.
// Imposta la proprietà "Multiline" su "true" per consentire al tag di contenere più righe di contenuto.
tag.Multiline = true;

// Imposta la proprietà "Appearance" su "SdtAppearance.Tags" per mostrare i tag attorno al contenuto.
 // Per impostazione predefinita, il tag del documento strutturato viene visualizzato come BoundingBox.
tag.Appearance = SdtAppearance.Tags;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(tag);

// Inserisce un clone del nostro tag di documento strutturato in un nuovo paragrafo.
StructuredDocumentTag tagClone = (StructuredDocumentTag)tag.Clone(true);
builder.InsertParagraph();
builder.InsertNode(tagClone);

// Usa il metodo "RemoveSelfOnly" per rimuovere un tag di documento strutturato, mantenendone il contenuto nel documento.
tagClone.RemoveSelfOnly();

doc.Save(ArtifactsDir + "StructuredDocumentTag.PlainText.docx");
```

### Guarda anche

* class [StructuredDocumentTag](../)
* spazio dei nomi [Aspose.Words.Markup](../../structureddocumenttag/)
* assemblea [Aspose.Words](../../../)


