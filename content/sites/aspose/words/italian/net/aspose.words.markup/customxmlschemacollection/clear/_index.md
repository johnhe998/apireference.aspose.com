---
title: CustomXmlSchemaCollection.Clear
second_title: Aspose.Words per .NET API Reference
description: CustomXmlSchemaCollection metodo. Rimuove tutti gli elementi dalla raccolta.
type: docs
weight: 40
url: /it/net/aspose.words.markup/customxmlschemacollection/clear/
---
## CustomXmlSchemaCollection.Clear method

Rimuove tutti gli elementi dalla raccolta.

```csharp
public void Clear()
```

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

* class [CustomXmlSchemaCollection](../)
* spazio dei nomi [Aspose.Words.Markup](../../customxmlschemacollection/)
* assemblea [Aspose.Words](../../../)


