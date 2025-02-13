---
title: Class CustomXmlSchemaCollection
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Markup.CustomXmlSchemaCollection classe. Una raccolta di stringhe che rappresentano schemi XML associati a una parte XML personalizzata.
type: docs
weight: 3720
url: /it/net/aspose.words.markup/customxmlschemacollection/
---
## CustomXmlSchemaCollection class

Una raccolta di stringhe che rappresentano schemi XML associati a una parte XML personalizzata.

```csharp
public class CustomXmlSchemaCollection : IEnumerable<string>
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Count](../../aspose.words.markup/customxmlschemacollection/count/) { get; } | Ottiene il numero di elementi contenuti nella raccolta. |
| [Item](../../aspose.words.markup/customxmlschemacollection/item/) { get; set; } | Ottiene o imposta l'elemento in corrispondenza dell'indice specificato. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [Add](../../aspose.words.markup/customxmlschemacollection/add/)(string) | Aggiunge un elemento alla raccolta. |
| [Clear](../../aspose.words.markup/customxmlschemacollection/clear/)() | Rimuove tutti gli elementi dalla raccolta. |
| [Clone](../../aspose.words.markup/customxmlschemacollection/clone/)() | Crea un clone profondo di questo oggetto. |
| [GetEnumerator](../../aspose.words.markup/customxmlschemacollection/getenumerator/)() | Restituisce un oggetto enumeratore che può essere utilizzato per scorrere tutti gli elementi della raccolta. |
| [IndexOf](../../aspose.words.markup/customxmlschemacollection/indexof/)(string) | Restituisce l'indice in base zero del valore specificato nella raccolta. |
| [Remove](../../aspose.words.markup/customxmlschemacollection/remove/)(string) | Rimuove il valore specificato dalla raccolta. |
| [RemoveAt](../../aspose.words.markup/customxmlschemacollection/removeat/)(int) | Rimuove un valore in corrispondenza dell'indice specificato. |

### Osservazioni

Non crei istanze di questa classe. Si accede alla raccolta di schemi XML di un codice XML personalizzato part tramite il file[`Schemas`](../customxmlpart/schemas/) proprietà.

### Esempi

Mostra come lavorare con una raccolta di schemi XML.

```csharp
Document doc = new Document();

string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Hello, World!</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);

// Aggiunge un'associazione dello schema XML.
xmlPart.Schemas.Add("http://www.w3.org/2001/XMLSchema");

// Clona la raccolta di associazioni dello schema XML della parte XML personalizzata,
// e quindi aggiungi un paio di nuovi schemi al clone.
CustomXmlSchemaCollection schemas = xmlPart.Schemas.Clone();
schemas.Add("http://www.w3.org/2001/XMLSchema-instance");
schemas.Add("http://schemas.microsoft.com/office/2006/metadata/contentType");

Assert.AreEqual(3, schemas.Count);
Assert.AreEqual(2, schemas.IndexOf("http://schemas.microsoft.com/office/2006/metadata/contentType"));

// Enumera gli schemi e stampa ogni elemento.
using (IEnumerator<string> enumerator = schemas.GetEnumerator())
{
    while (enumerator.MoveNext())
        Console.WriteLine(enumerator.Current);
}

// Di seguito sono riportati tre modi per rimuovere gli schemi dalla raccolta.
// 1 - Rimuove uno schema per indice:
schemas.RemoveAt(2);

// 2 - Rimuove uno schema per valore:
schemas.Remove("http://www.w3.org/2001/XMLSchema");

// 3 - Usa il metodo "Cancella" per svuotare la raccolta in una volta.
schemas.Clear();

Assert.AreEqual(0, schemas.Count);
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Markup](../../aspose.words.markup/)
* assemblea [Aspose.Words](../../)


