---
title: Comment.AddReply
second_title: Aspose.Words per .NET API Reference
description: Comment metodo. Aggiunge una risposta a questo commento.
type: docs
weight: 120
url: /it/net/aspose.words/comment/addreply/
---
## Comment.AddReply method

Aggiunge una risposta a questo commento.

```csharp
public Comment AddReply(string author, string initial, DateTime dateTime, string text)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| author | String | Il nome dell'autore per la risposta. |
| initial | String | L'autore sigla per la risposta. |
| dateTime | DateTime | La data e l'ora della risposta. |
| text | String | Il testo di risposta. |

### Valore di ritorno

Il creato[`Comment`](../) nodo per la risposta.

### Osservazioni

A causa delle limitazioni di MS Office esistenti, nel documento è consentito solo 1 livello di risposte. Un'eccezione di tipoInvalidOperationException verrà generato se questo metodo viene chiamato sul commento di risposta esistente.

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


