---
title: CustomXmlProperty.Uri
second_title: Aspose.Words per .NET API Reference
description: CustomXmlProperty proprietà. Ottiene o imposta lURI dello spazio dei nomi dellattributo XML personalizzato o della proprietà dello smart tag.
type: docs
weight: 30
url: /it/net/aspose.words.markup/customxmlproperty/uri/
---
## CustomXmlProperty.Uri property

Ottiene o imposta l'URI dello spazio dei nomi dell'attributo XML personalizzato o della proprietà dello smart tag.

```csharp
public string Uri { get; set; }
```

### Osservazioni

Non può essere nullo.

L'impostazione predefinita è una stringa vuota.

### Esempi

Mostra come lavorare con le proprietà degli smart tag per ottenere informazioni approfondite sugli smart tag.

```csharp
Document doc = new Document(MyDir + "Smart tags.doc");

// Uno smart tag appare in un documento con Microsoft Word riconosce una parte del suo testo come una forma di dati,
// come un nome, una data o un indirizzo e lo converte in un collegamento ipertestuale che visualizza una sottolineatura tratteggiata viola.
// In Word 2003, possiamo abilitare gli smart tag tramite "Strumenti" -> "Opzioni di correzione automatica..." -> "SmartTag".
// Nel nostro documento di input, ci sono tre oggetti che Microsoft Word ha registrato come smart tag.
// Gli smart tag possono essere nidificati, quindi questa raccolta ne contiene di più.
SmartTag[] smartTags = doc.GetChildNodes(NodeType.SmartTag, true).OfType<SmartTag>().ToArray();

Assert.AreEqual(8, smartTags.Length);

// Il membro "Proprietà" di uno smart tag contiene i relativi metadati, che saranno diversi per ogni tipo di smart tag.
// Le proprietà di uno smart tag di tipo "data" contengono anno, mese e giorno.
CustomXmlPropertyCollection properties = smartTags[7].Properties;

Assert.AreEqual(4, properties.Count);

using (IEnumerator<CustomXmlProperty> enumerator = properties.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Property name: {enumerator.Current.Name}, value: {enumerator.Current.Value}");
        Assert.AreEqual("", enumerator.Current.Uri);
    }
}

// Possiamo anche accedere alle proprietà in vari modi, ad esempio una coppia chiave-valore.
Assert.True(properties.Contains("Day"));
Assert.AreEqual("22", properties["Day"].Value);
Assert.AreEqual("2003", properties[2].Value);
Assert.AreEqual(1, properties.IndexOfKey("Month"));

// Di seguito sono riportati tre modi per rimuovere elementi dalla raccolta delle proprietà.
// 1 - Rimuovi per indice:
properties.RemoveAt(3);

Assert.AreEqual(3, properties.Count);

// 2 - Rimuovi per nome:
properties.Remove("Year");

Assert.AreEqual(2, properties.Count);

// 3 - Cancella l'intera collezione in una volta:
properties.Clear();

Assert.AreEqual(0, properties.Count);
```

### Guarda anche

* class [CustomXmlProperty](../)
* spazio dei nomi [Aspose.Words.Markup](../../customxmlproperty/)
* assemblea [Aspose.Words](../../../)


