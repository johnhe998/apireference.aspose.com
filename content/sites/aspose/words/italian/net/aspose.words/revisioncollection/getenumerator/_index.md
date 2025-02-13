---
title: RevisionCollection.GetEnumerator
second_title: Aspose.Words per .NET API Reference
description: RevisionCollection metodo. Restituisce un oggetto enumeratore.
type: docs
weight: 50
url: /it/net/aspose.words/revisioncollection/getenumerator/
---
## RevisionCollection.GetEnumerator method

Restituisce un oggetto enumeratore.

```csharp
public IEnumerator<Revision> GetEnumerator()
```

### Esempi

Mostra come lavorare con la raccolta di revisioni di un documento.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
RevisionCollection revisions = doc.Revisions;

// Questa raccolta stessa ha una raccolta di gruppi di revisione.
// Ogni gruppo è una sequenza di revisioni adiacenti.
Console.WriteLine($"{revisions.Groups.Count} revision groups:");

// Iterare sulla raccolta di gruppi e stampare il testo che riguarda la revisione.
using (IEnumerator<RevisionGroup> e = revisions.Groups.GetEnumerator())
{
    while (e.MoveNext())
    {
        Console.WriteLine($"\tGroup type \"{e.Current.RevisionType}\", " +
                          $"author: {e.Current.Author}, contents: [{e.Current.Text.Trim()}]");
    }
}

// Ogni esecuzione che interessa una revisione ottiene un oggetto Revisione corrispondente.
// La raccolta delle revisioni è considerevolmente più ampia della forma condensata che abbiamo stampato sopra,
// a seconda di quante esecuzioni abbiamo segmentato il documento durante la modifica di Microsoft Word.
Console.WriteLine($"\n{revisions.Count} revisions:");

using (IEnumerator<Revision> e = revisions.GetEnumerator())
{
    while (e.MoveNext())
    {
        // Un StyleDefinitionChange influisce rigorosamente sugli stili e non sui nodi del documento. Questo significa "Stile Genitore"
        // la proprietà sarà sempre in uso, mentre ParentNode sarà sempre null.
        // Poiché tutte le altre modifiche interessano i nodi, ParentNode sarà al contrario in uso e ParentStyle sarà nullo.
        if (e.Current.RevisionType == RevisionType.StyleDefinitionChange)
        {
            Console.WriteLine($"\tRevision type \"{e.Current.RevisionType}\", " +
                              $"author: {e.Current.Author}, style: [{e.Current.ParentStyle.Name}]");
        }
        else
        {
            Console.WriteLine($"\tRevision type \"{e.Current.RevisionType}\", " +
                              $"author: {e.Current.Author}, contents: [{e.Current.ParentNode.GetText().Trim()}]");
        }
    }
}

// Rifiuta tutte le revisioni tramite la raccolta, riportando il documento alla sua forma originale.
revisions.RejectAll();

Assert.AreEqual(0, revisions.Count);
```

### Guarda anche

* class [Revision](../../revision/)
* class [RevisionCollection](../)
* spazio dei nomi [Aspose.Words](../../revisioncollection/)
* assemblea [Aspose.Words](../../../)


