---
title: XmlMapping.SetMapping
second_title: Aspose.Words per .NET API Reference
description: XmlMapping metodo. Imposta un mapping tra il tag del documento strutturato padre e un nodo XML di una parte di dati XML personalizzata.
type: docs
weight: 70
url: /it/net/aspose.words.markup/xmlmapping/setmapping/
---
## XmlMapping.SetMapping method

Imposta un mapping tra il tag del documento strutturato padre e un nodo XML di una parte di dati XML personalizzata.

```csharp
public bool SetMapping(CustomXmlPart customXmlPart, string xPath, string prefixMapping)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| customXmlPart | CustomXmlPart | Una parte di dati XML personalizzata su cui eseguire il mapping. |
| xPath | String | Un'espressione XPath per trovare il nodo XML. |
| prefixMapping | String | Mappature del prefisso dello spazio dei nomi XML per valutare l'XPath. |

### Valore di ritorno

Un flag che indica se il tag del documento strutturato padre è stato mappato correttamente su il nodo XML.

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

* class [CustomXmlPart](../../customxmlpart/)
* class [XmlMapping](../)
* spazio dei nomi [Aspose.Words.Markup](../../xmlmapping/)
* assemblea [Aspose.Words](../../../)


