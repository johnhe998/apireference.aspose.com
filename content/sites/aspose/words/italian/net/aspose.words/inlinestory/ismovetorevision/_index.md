---
title: InlineStory.IsMoveToRevision
second_title: Aspose.Words per .NET API Reference
description: InlineStory proprietà. Restituisce VERO se questo oggetto è stato spostato inserito in Microsoft Word mentre era abilitato il rilevamento delle modifiche.
type: docs
weight: 60
url: /it/net/aspose.words/inlinestory/ismovetorevision/
---
## InlineStory.IsMoveToRevision property

Restituisce **VERO** se questo oggetto è stato spostato (inserito) in Microsoft Word mentre era abilitato il rilevamento delle modifiche.

```csharp
public bool IsMoveToRevision { get; }
```

### Esempi

Mostra come visualizzare le proprietà relative alla revisione dei nodi InlineStory.

```csharp
Document doc = new Document(MyDir + "Revision footnotes.docx");

// Quando modifichiamo il documento mentre l'opzione "Traccia modifiche", che si trova in tramite Revisione -> monitoraggio,
// è attivato in Microsoft Word, le modifiche che applichiamo contano come revisioni.
// Quando modifichiamo un documento usando Aspose.Words, possiamo iniziare a tenere traccia delle revisioni da
// richiamando il metodo "StartTrackRevisions" del documento e interrompendo il rilevamento utilizzando il metodo "StopTrackRevisions".
// Possiamo accettare revisioni per assimilarle al documento
// o rifiutarli per annullare ed eliminare la modifica proposta.
Assert.IsTrue(doc.HasRevisions);

List<Footnote> footnotes = doc.GetChildNodes(NodeType.Footnote, true).Cast<Footnote>().ToList();

Assert.AreEqual(5, footnotes.Count);

// Di seguito sono riportati cinque tipi di revisioni che possono contrassegnare un nodo InlineStory.
// 1 - Una revisione "inserto":
// Questa revisione si verifica quando inseriamo del testo durante il rilevamento delle modifiche.
Assert.IsTrue(footnotes[2].IsInsertRevision);

// 2 - Una revisione "sposta da":
// Quando evidenziamo il testo in Microsoft Word, quindi lo trasciniamo in una posizione diversa nel documento
// durante il rilevamento delle modifiche, vengono visualizzate due revisioni.
// La revisione "sposta da" è una copia del testo originariamente prima dello spostamento.
Assert.IsTrue(footnotes[4].IsMoveFromRevision);

// 3 - Una revisione "passa a":
// La revisione "sposta in" è il testo che abbiamo spostato nella sua nuova posizione nel documento.
// Le revisioni "Sposta da" e "Sposta in" appaiono in coppia per ogni revisione di spostamento che eseguiamo.
// L'accettazione di una revisione di spostamento elimina la revisione "sposta da" e il suo testo,
// e mantiene il testo della revisione "sposta in".
// Il rifiuto di una revisione di spostamento, al contrario, mantiene la revisione "sposta da" ed elimina la revisione "sposta in".
Assert.IsTrue(footnotes[1].IsMoveToRevision);

// 4 - Una revisione "cancella":
// Questa revisione si verifica quando eliminiamo il testo durante il rilevamento delle modifiche. Quando cancelliamo un testo come questo,
// rimarrà nel documento come revisione fino a quando non accettiamo la revisione,
// che cancellerà definitivamente il testo, o rifiuterà la revisione, che manterrà il testo che abbiamo eliminato dove era.
Assert.IsTrue(footnotes[3].IsDeleteRevision);
```

### Guarda anche

* class [InlineStory](../)
* spazio dei nomi [Aspose.Words](../../inlinestory/)
* assemblea [Aspose.Words](../../../)


