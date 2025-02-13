---
title: BuiltInDocumentProperties.HeadingPairs
second_title: Aspose.Words per .NET API Reference
description: BuiltInDocumentProperties proprietà. Specifica le intestazioni del documento e i relativi nomi.
type: docs
weight: 110
url: /it/net/aspose.words.properties/builtindocumentproperties/headingpairs/
---
## BuiltInDocumentProperties.HeadingPairs property

Specifica le intestazioni del documento e i relativi nomi.

```csharp
public object[] HeadingPairs { get; set; }
```

### Osservazioni

Ogni coppia di intestazioni occupa due elementi in questa matrice.

Il primo elemento della coppia è aString e specifica il nome dell'intestazione. Il secondo elemento della coppia è anInt32 e specifica il conteggio delle parti document per questa intestazione nel file[`TitlesOfParts`](../titlesofparts/) proprietà.

La somma totale dei conteggi per tutte le coppie di intestazioni in questa proprietà deve essere uguale al numero di elementi nella[`TitlesOfParts`](../titlesofparts/) proprietà.

Aspose.Words non aggiorna questa proprietà.

### Esempi

Mostra la relazione tra le proprietà "HeadingPairs" e "TitlesOfParts".

```csharp
Document doc = new Document(MyDir + "Heading pairs and titles of parts.docx");

// Possiamo trovare i valori combinati di queste collezioni tramite
// "File" -> "Proprietà" -> "Proprietà avanzate" -> Scheda "Contenuti".
// La proprietà HeadingPairs è una raccolta di <string, int> accoppia quello
// determina quante parti del documento si estende su un'intestazione.
object[] headingPairs = doc.BuiltInDocumentProperties.HeadingPairs;

// La proprietà TitlesOfParts contiene i nomi delle parti che appartengono alle intestazioni precedenti.
string[] titlesOfParts = doc.BuiltInDocumentProperties.TitlesOfParts;

int headingPairsIndex = 0;
int titlesOfPartsIndex = 0;
while (headingPairsIndex < headingPairs.Length)
{
    Console.WriteLine($"Parts for {headingPairs[headingPairsIndex++]}:");
    int partsCount = Convert.ToInt32(headingPairs[headingPairsIndex++]);

    for (int i = 0; i < partsCount; i++)
        Console.WriteLine($"\t\"{titlesOfParts[titlesOfPartsIndex++]}\"");
}
```

### Guarda anche

* class [BuiltInDocumentProperties](../)
* spazio dei nomi [Aspose.Words.Properties](../../builtindocumentproperties/)
* assemblea [Aspose.Words](../../../)


