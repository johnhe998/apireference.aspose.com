---
title: Class SectionCollection
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.SectionCollection classe. Una raccolta di Sezione oggetti nel documento.
type: docs
weight: 5450
url: /it/net/aspose.words/sectioncollection/
---
## SectionCollection class

Una raccolta di **Sezione** oggetti nel documento.

```csharp
public class SectionCollection : NodeCollection
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | Ottiene il numero di nodi nella raccolta. |
| [Item](../../aspose.words/sectioncollection/item/) { get; } | Recupera una sezione in corrispondenza dell'indice specificato. (2 indexers) |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [Add](../../aspose.words/nodecollection/add/)(Node) | Aggiunge un nodo alla fine della raccolta. |
| [Clear](../../aspose.words/nodecollection/clear/)() | Rimuove tutti i nodi da questa raccolta e dal documento. |
| [Contains](../../aspose.words/nodecollection/contains/)(Node) | Determina se un nodo è nella raccolta. |
| [GetEnumerator](../../aspose.words/nodecollection/getenumerator/)() | Fornisce una semplice iterazione di stile "foreach" sulla raccolta di nodi. |
| [IndexOf](../../aspose.words/nodecollection/indexof/)(Node) | Restituisce l'indice in base zero del nodo specificato. |
| [Insert](../../aspose.words/nodecollection/insert/)(int, Node) | Inserisce un nodo nella raccolta in corrispondenza dell'indice specificato. |
| [Remove](../../aspose.words/nodecollection/remove/)(Node) | Rimuove il nodo dalla raccolta e dal documento. |
| [RemoveAt](../../aspose.words/nodecollection/removeat/)(int) | Rimuove il nodo in corrispondenza dell'indice specificato dalla raccolta e dal documento. |
| [ToArray](../../aspose.words/sectioncollection/toarray/#toarray_1)() | Copia tutte le sezioni dalla raccolta in un nuovo array di sezioni. (2 methods) |

### Osservazioni

Un documento di Microsoft Word può contenere più sezioni. Per creare una sezione in un Microsoft Word, seleziona il comando Inserisci/Interrompi e seleziona un tipo di interruzione. L'interruzione specifica se la sezione inizia su una nuova pagina o sulla stessa pagina.

L'inserimento e la rimozione di sezioni a livello di codice possono essere utilizzati per personalizzare i documenti prodotti durante la stampa unione. Se un documento deve avere contenuto o parti di differenti a seconda di alcuni criteri, puoi creare un documento "master" che contenga più sezioni ed eliminare alcune delle sezioni prima o dopo la stampa unione.

### Esempi

Mostra come aggiungere e rimuovere sezioni in un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");

Assert.AreEqual("Section 1\x000cSection 2", doc.GetText().Trim());

// Elimina la prima sezione dal documento.
doc.Sections.RemoveAt(0);

Assert.AreEqual("Section 2", doc.GetText().Trim());

// Aggiungi una copia di quella che ora è la prima sezione alla fine del documento.
int lastSectionIdx = doc.Sections.Count - 1;
Section newSection = doc.Sections[lastSectionIdx].Clone();
doc.Sections.Add(newSection);

Assert.AreEqual("Section 2\x000cSection 2", doc.GetText().Trim());
```

### Guarda anche

* class [NodeCollection](../nodecollection/)
* spazio dei nomi [Aspose.Words](../../aspose.words/)
* assemblea [Aspose.Words](../../)


