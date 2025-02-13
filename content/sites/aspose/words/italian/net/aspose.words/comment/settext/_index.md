---
title: Comment.SetText
second_title: Aspose.Words per .NET API Reference
description: Comment metodo. Questo è un metodo pratico che permette di impostare facilmente il testo del commento.
type: docs
weight: 150
url: /it/net/aspose.words/comment/settext/
---
## Comment.SetText method

Questo è un metodo pratico che permette di impostare facilmente il testo del commento.

```csharp
public void SetText(string text)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| text | String | Il nuovo testo del commento. |

### Osservazioni

Questo metodo consente di impostare rapidamente il testo di un commento da una stringa. La stringa può contenere interruzioni di paragrafo, questo creerà paragrafi di testo nel commento di conseguenza. Se vuoi inserire elementi più complessi nel commento, ad esempio bookmarks o tabelle o applicare la formattazione avanzata, devi usare le classi di nodi appropriate a costruire il testo del commento.

### Esempi

Mostra come aggiungere un commento a un documento e quindi rispondere ad esso.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Comment comment = new Comment(doc, "John Doe", "J.D.", DateTime.Now);
comment.SetText("My comment.");

// Posiziona il commento su un nodo nel corpo del documento.
// Questo commento apparirà nella posizione del suo paragrafo,
// al di fuori del margine destro della pagina e con una linea tratteggiata che lo collega al paragrafo.
builder.CurrentParagraph.AppendChild(comment);

// Aggiungi una risposta, che apparirà sotto il suo commento principale.
comment.AddReply("Joe Bloggs", "J.B.", DateTime.Now, "New reply");

// Commenti e risposte sono entrambi nodi Commenti.
Assert.AreEqual(2, doc.GetChildNodes(NodeType.Comment, true).Count);

// I commenti che non rispondono ad altri commenti sono di "livello superiore". Non hanno commenti sugli antenati.
Assert.Null(comment.Ancestor);

// Le risposte hanno un commento di livello superiore dell'antenato.
Assert.AreEqual(comment, comment.Replies[0].Ancestor);

doc.Save(ArtifactsDir + "Comment.AddCommentWithReply.docx");
```

### Guarda anche

* class [Comment](../)
* spazio dei nomi [Aspose.Words](../../comment/)
* assemblea [Aspose.Words](../../../)


