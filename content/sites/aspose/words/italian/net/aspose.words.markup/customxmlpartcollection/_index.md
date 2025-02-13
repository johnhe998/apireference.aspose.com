---
title: Class CustomXmlPartCollection
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Markup.CustomXmlPartCollection classe. Rappresenta una raccolta di parti XML personalizzate. Gli articoli sonoCustomXmlPart oggetti.
type: docs
weight: 3690
url: /it/net/aspose.words.markup/customxmlpartcollection/
---
## CustomXmlPartCollection class

Rappresenta una raccolta di parti XML personalizzate. Gli articoli sono[`CustomXmlPart`](../customxmlpart/) oggetti.

```csharp
public class CustomXmlPartCollection : IEnumerable<CustomXmlPart>
```

## Costruttori

| Nome | Descrizione |
| --- | --- |
| [CustomXmlPartCollection](customxmlpartcollection/)() | Default_Costruttore |

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Count](../../aspose.words.markup/customxmlpartcollection/count/) { get; } | Ottiene il numero di elementi contenuti nella raccolta. |
| [Item](../../aspose.words.markup/customxmlpartcollection/item/) { get; set; } | Ottiene o imposta un elemento all'indice specificato. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [Add](../../aspose.words.markup/customxmlpartcollection/add/#add_1)(CustomXmlPart) | Aggiunge un elemento alla raccolta. |
| [Add](../../aspose.words.markup/customxmlpartcollection/add/#add)(string, string) | Crea una nuova parte XML con l'XML specificato e la aggiunge alla raccolta. |
| [Clear](../../aspose.words.markup/customxmlpartcollection/clear/)() | Rimuove tutti gli elementi dalla raccolta. |
| [Clone](../../aspose.words.markup/customxmlpartcollection/clone/)() | Crea una copia completa di questa raccolta e dei suoi elementi. |
| [GetById](../../aspose.words.markup/customxmlpartcollection/getbyid/)(string) | Trova e restituisce una parte XML personalizzata in base al suo identificatore. |
| [GetEnumerator](../../aspose.words.markup/customxmlpartcollection/getenumerator/)() | Restituisce un oggetto enumeratore che può essere utilizzato per scorrere tutti gli elementi della raccolta. |
| [RemoveAt](../../aspose.words.markup/customxmlpartcollection/removeat/)(int) | Rimuove un elemento all'indice specificato. |

### Osservazioni

Normalmente non è necessario creare istanze di questa classe. È possibile accedere ai dati XML personalizzati archiviati in un documento tramite il[`CustomXmlParts`](../../aspose.words/document/customxmlparts/) proprietà.

### Esempi

Mostra come creare un tag di documento strutturato con dati XML personalizzati.

```csharp
Document doc = new Document();

// Costruisci una parte XML che contiene dati e aggiungila alla raccolta del documento.
// Se abilitiamo la scheda "Sviluppatore" in Microsoft Word,
// possiamo trovare elementi di questa raccolta nel "Riquadro mappatura XML", insieme ad alcuni elementi predefiniti.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Hello world!</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);

Assert.AreEqual(Encoding.ASCII.GetBytes(xmlPartContent), xmlPart.Data);
Assert.AreEqual(xmlPartId, xmlPart.Id);

// Di seguito sono riportati due modi per fare riferimento alle parti XML.
// 1 - Da un indice nella raccolta di parti XML personalizzata:
Assert.AreEqual(xmlPart, doc.CustomXmlParts[0]);

// 2 - Per GUID:
Assert.AreEqual(xmlPart, doc.CustomXmlParts.GetById(xmlPartId));

// Aggiunge un'associazione dello schema XML.
xmlPart.Schemas.Add("http://www.w3.org/2001/XMLSchema");

// Clona una parte, quindi inseriscila nella raccolta.
CustomXmlPart xmlPartClone = xmlPart.Clone();
xmlPartClone.Id = Guid.NewGuid().ToString("B");
doc.CustomXmlParts.Add(xmlPartClone);

Assert.AreEqual(2, doc.CustomXmlParts.Count);

// Scorri la raccolta e stampa il contenuto di ciascuna parte.
using (IEnumerator<CustomXmlPart> enumerator = doc.CustomXmlParts.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"XML part index {index}, ID: {enumerator.Current.Id}");
        Console.WriteLine($"\tContent: {Encoding.UTF8.GetString(enumerator.Current.Data)}");
        index++;
    }
}

// Usa il metodo "RemoveAt" per rimuovere la parte clonata per indice.
doc.CustomXmlParts.RemoveAt(1);

Assert.AreEqual(1, doc.CustomXmlParts.Count);

// Clona la raccolta di parti XML, quindi usa il metodo "Clear" per rimuovere tutti i suoi elementi contemporaneamente.
CustomXmlPartCollection customXmlParts = doc.CustomXmlParts.Clone();
customXmlParts.Clear();

// Crea un tag di documento strutturato che visualizzerà il contenuto della nostra parte e lo inserirà nel corpo del documento.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
tag.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", string.Empty);

doc.FirstSection.Body.AppendChild(tag);

doc.Save(ArtifactsDir + "StructuredDocumentTag.CustomXml.docx");
```

### Guarda anche

* class [CustomXmlPart](../customxmlpart/)
* spazio dei nomi [Aspose.Words.Markup](../../aspose.words.markup/)
* assemblea [Aspose.Words](../../)


