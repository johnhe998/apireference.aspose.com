---
title: BuiltInDocumentProperties.TitlesOfParts
second_title: Aspose.Words per .NET API Reference
description: BuiltInDocumentProperties proprietà. Ogni stringa nellarray specifica il nome di una parte nel documento.
type: docs
weight: 300
url: /it/net/aspose.words.properties/builtindocumentproperties/titlesofparts/
---
## BuiltInDocumentProperties.TitlesOfParts property

Ogni stringa nell'array specifica il nome di una parte nel documento.

```csharp
public string[] TitlesOfParts { get; set; }
```

### Osservazioni

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


