---
title: OdsoRecipientData.Active
second_title: Aspose.Words per .NET API Reference
description: OdsoRecipientData proprietà. Specifica se il record dallorigine dati deve essere importato in un documento quando viene eseguita la stampa unione. Il valore predefinito èVERO .
type: docs
weight: 20
url: /it/net/aspose.words.settings/odsorecipientdata/active/
---
## OdsoRecipientData.Active property

Specifica se il record dall'origine dati deve essere importato in un documento quando viene eseguita la stampa unione. Il valore predefinito è`VERO` .

```csharp
public bool Active { get; set; }
```

### Esempi

Mostra come accedere alla raccolta di dati che designa quali record di origine dati unire verranno esclusi da un'unione di posta.

```csharp
Document doc = new Document(MyDir + "Odso data.docx");

OdsoRecipientDataCollection dataCollection = doc.MailMergeSettings.Odso.RecipientDatas;

Assert.AreEqual(70, dataCollection.Count);

using (IEnumerator<OdsoRecipientData> enumerator = dataCollection.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine(
            $"Odso recipient data index {index++} will {(enumerator.Current.Active ? "" : "not ")}be imported upon mail merge.");
        Console.WriteLine($"\tColumn #{enumerator.Current.Column}");
        Console.WriteLine($"\tHash code: {enumerator.Current.Hash}");
        Console.WriteLine($"\tContents array length: {enumerator.Current.UniqueTag.Length}");
    }
}

// Possiamo clonare gli elementi in questa raccolta.
Assert.AreNotEqual(dataCollection[0], dataCollection[0].Clone());

// Possiamo anche rimuovere elementi singolarmente o cancellare l'intera raccolta in una volta.
dataCollection.RemoveAt(0);

Assert.AreEqual(69, dataCollection.Count);

dataCollection.Clear();

Assert.AreEqual(0, dataCollection.Count);
```

### Guarda anche

* class [OdsoRecipientData](../)
* spazio dei nomi [Aspose.Words.Settings](../../odsorecipientdata/)
* assemblea [Aspose.Words](../../../)


