---
title: Class RevisionCollection
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.RevisionCollection classe. Una raccolta diRevision oggetti che rappresentano le revisioni nel documento.
type: docs
weight: 4510
url: /it/net/aspose.words/revisioncollection/
---
## RevisionCollection class

Una raccolta di[`Revision`](../revision/) oggetti che rappresentano le revisioni nel documento.

```csharp
public class RevisionCollection : IEnumerable<Revision>
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Count](../../aspose.words/revisioncollection/count/) { get; } | Restituisce il numero di revisioni nella raccolta. |
| [Groups](../../aspose.words/revisioncollection/groups/) { get; } | Raccolta di gruppi di revisione. |
| [Item](../../aspose.words/revisioncollection/item/) { get; } | Restituisce una revisione all'indice specificato. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [AcceptAll](../../aspose.words/revisioncollection/acceptall/)() | Accetta tutte le revisioni in questa raccolta. |
| [GetEnumerator](../../aspose.words/revisioncollection/getenumerator/)() | Restituisce un oggetto enumeratore. |
| [RejectAll](../../aspose.words/revisioncollection/rejectall/)() | Rifiuta tutte le revisioni in questa raccolta. |

### Osservazioni

Non crei direttamente istanze di questa classe. Utilizzare il[`Revisions`](../document/revisions/) proprietà per ottenere le revisioni presenti in un documento.

### Esempi

Mostra come lavorare con le revisioni in un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// La normale modifica del documento non conta come revisione.
builder.Write("This does not count as a revision. ");

Assert.IsFalse(doc.HasRevisions);

// Per registrare le nostre modifiche come revisioni, dobbiamo dichiarare un autore e quindi iniziare a seguirle.
doc.StartTrackRevisions("John Doe", DateTime.Now);

builder.Write("This is revision #1. ");

Assert.IsTrue(doc.HasRevisions);
Assert.AreEqual(1, doc.Revisions.Count);

// Questo flag corrisponde a "Revisione" -> "Tracciamento" -> Opzione "Traccia modifiche" in Microsoft Word.
// Il metodo "StartTrackRevisions" non influisce sul suo valore,
// e il documento tiene traccia delle revisioni a livello di codice nonostante abbia un valore di "false".
// Se apriamo questo documento utilizzando Microsoft Word, non terrà traccia delle revisioni.
Assert.IsFalse(doc.TrackRevisions);

// Abbiamo aggiunto del testo utilizzando il generatore di documenti, quindi la prima revisione è una revisione di tipo inserimento.
Revision revision = doc.Revisions[0];
Assert.AreEqual("John Doe", revision.Author);
Assert.AreEqual("This is revision #1. ", revision.ParentNode.GetText());
Assert.AreEqual(RevisionType.Insertion, revision.RevisionType);
Assert.AreEqual(revision.DateTime.Date, DateTime.Now.Date);
Assert.AreEqual(doc.Revisions.Groups[0], revision.Group);

// Rimuove una corsa per creare una revisione del tipo di eliminazione.
doc.FirstSection.Body.FirstParagraph.Runs[0].Remove();

// L'aggiunta di una nuova revisione la pone all'inizio della raccolta di revisioni.
Assert.AreEqual(RevisionType.Deletion, doc.Revisions[0].RevisionType);
Assert.AreEqual(2, doc.Revisions.Count);

// Le revisioni degli inserti vengono visualizzate nel corpo del documento anche prima che accettiamo/rifiutiamo la revisione.
// Il rifiuto della revisione rimuoverà i suoi nodi dal corpo. Al contrario, i nodi che compongono eliminano le revisioni
// indugiare anche nel documento finché non accettiamo la revisione.
Assert.AreEqual("This does not count as a revision. This is revision #1.", doc.GetText().Trim());

// L'accettazione della revisione di eliminazione rimuoverà il relativo nodo padre dal testo del paragrafo
// e quindi rimuovere la revisione della raccolta stessa.
doc.Revisions[0].Accept();

Assert.AreEqual(1, doc.Revisions.Count);
Assert.AreEqual("This is revision #1.", doc.GetText().Trim());

builder.Writeln("");
builder.Write("This is revision #2.");

// Ora sposta il nodo per creare un tipo di revisione mobile.
Node node = doc.FirstSection.Body.Paragraphs[1];
Node endNode = doc.FirstSection.Body.Paragraphs[1].NextSibling;
Node referenceNode = doc.FirstSection.Body.Paragraphs[0];

while (node != endNode)
{
    Node nextNode = node.NextSibling;
    doc.FirstSection.Body.InsertBefore(node, referenceNode);
    node = nextNode;
}

Assert.AreEqual(RevisionType.Moving, doc.Revisions[0].RevisionType);
Assert.AreEqual(8, doc.Revisions.Count);
Assert.AreEqual("This is revision #2.\rThis is revision #1. \rThis is revision #2.", doc.GetText().Trim());

// La revisione in movimento è ora all'indice 1. Rifiuta la revisione per eliminarne il contenuto.
doc.Revisions[1].Reject();

Assert.AreEqual(6, doc.Revisions.Count);
Assert.AreEqual("This is revision #1. \rThis is revision #2.", doc.GetText().Trim());
```

### Guarda anche

* class [Revision](../revision/)
* spazio dei nomi [Aspose.Words](../../aspose.words/)
* assemblea [Aspose.Words](../../)


