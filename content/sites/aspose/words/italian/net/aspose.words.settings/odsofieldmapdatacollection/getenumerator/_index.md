---
title: OdsoFieldMapDataCollection.GetEnumerator
second_title: Aspose.Words per .NET API Reference
description: OdsoFieldMapDataCollection metodo. Restituisce un oggetto enumeratore che può essere utilizzato per scorrere tutti gli elementi della raccolta.
type: docs
weight: 60
url: /it/net/aspose.words.settings/odsofieldmapdatacollection/getenumerator/
---
## OdsoFieldMapDataCollection.GetEnumerator method

Restituisce un oggetto enumeratore che può essere utilizzato per scorrere tutti gli elementi della raccolta.

```csharp
public IEnumerator<OdsoFieldMapData> GetEnumerator()
```

### Esempi

Mostra come accedere alla raccolta di dati che mappa le colonne dell'origine dati per unire i campi.

```csharp
Document doc = new Document(MyDir + "Odso data.docx");

// Questa raccolta definisce come una stampa unione mapperà le colonne da un'origine dati
// ai campi MERGEFIELD, ADDRESSBLOCK e GREETINGLINE.
OdsoFieldMapDataCollection dataCollection = doc.MailMergeSettings.Odso.FieldMapDatas;
Assert.AreEqual(30, dataCollection.Count);

using (IEnumerator<OdsoFieldMapData> enumerator = dataCollection.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Field map data index {index++}, type \"{enumerator.Current.Type}\":");

        Console.WriteLine(
            enumerator.Current.Type != OdsoFieldMappingType.Null
                ? $"\tColumn \"{enumerator.Current.Name}\", number {enumerator.Current.Column} mapped to merge field \"{enumerator.Current.MappedName}\"."
                : "\tNo valid column to field mapping data present.");
    }
}

// Clona gli elementi in questa raccolta.
Assert.AreNotEqual(dataCollection[0], dataCollection[0].Clone());

// Usa gli elementi del metodo "RemoveAt" individualmente per indice.
dataCollection.RemoveAt(0);

Assert.AreEqual(29, dataCollection.Count);

// Usa il metodo "Cancella" per cancellare l'intera collezione in una volta.
dataCollection.Clear();

Assert.AreEqual(0, dataCollection.Count);
```

### Guarda anche

* class [OdsoFieldMapData](../../odsofieldmapdata/)
* class [OdsoFieldMapDataCollection](../)
* spazio dei nomi [Aspose.Words.Settings](../../odsofieldmapdatacollection/)
* assemblea [Aspose.Words](../../../)


