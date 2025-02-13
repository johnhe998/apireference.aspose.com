---
title: Class CustomPart
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Markup.CustomPart classe. Rappresenta una parte personalizzata contenuto arbitrario non definita dallo standard ISO/IEC 29500.
type: docs
weight: 3660
url: /it/net/aspose.words.markup/custompart/
---
## CustomPart class

Rappresenta una parte personalizzata (contenuto arbitrario), non definita dallo standard ISO/IEC 29500.

```csharp
public class CustomPart
```

## Costruttori

| Nome | Descrizione |
| --- | --- |
| [CustomPart](custompart/)() | Default_Costruttore |

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [ContentType](../../aspose.words.markup/custompart/contenttype/) { get; set; } | Specifica il tipo di contenuto di questa parte personalizzata. |
| [Data](../../aspose.words.markup/custompart/data/) { get; set; } | Contiene i dati di questa parte personalizzata. |
| [IsExternal](../../aspose.words.markup/custompart/isexternal/) { get; set; } | `Falso` se questa parte personalizzata è memorizzata all'interno del pacchetto OOXML.`Vero` se questa parte personalizzata è una destinazione esterna. |
| [Name](../../aspose.words.markup/custompart/name/) { get; set; } | Ottiene o imposta il nome assoluto di questa parte all'interno del pacchetto OOXML o l'URL di destinazione. |
| [RelationshipType](../../aspose.words.markup/custompart/relationshiptype/) { get; set; } | Ottiene o imposta il tipo di relazione dalla parte padre a questa parte personalizzata. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [Clone](../../aspose.words.markup/custompart/clone/)() | Crea una copia "abbastanza profonda" dell'oggetto. Non duplica i byte del file[`Data`](./data/) valore. |

### Osservazioni

Questa classe rappresenta una parte OOXML che è la destinazione di una "relazione sconosciuta". Tutte le relazioni non definite in ISO/IEC 29500 sono considerate "relazioni sconosciute". Le relazioni sconosciute sono consentite all'interno di un documento Office Open XML a condizione che siano conformi alle linee guida del markup delle relazioni.

Microsoft Word conserva le parti personalizzate durante i cicli di apertura/salvataggio. Alcune informazioni aggiuntive possono essere trovate qui http://blogs.msdn.com/dmahugh/archive/2006/11/25/arbitrary-content-in-an-opc-package.aspx

Aspose.Words esegue anche il roundtrip di parti personalizzate e, inoltre, consente di accedere a livello di codice a tali parti tramite il`CustomPart` e[`CustomPartCollection`](../custompartcollection/) oggetti.

Non confondere le parti personalizzate con i dati XML personalizzati. Uso[`CustomXmlPart`](../customxmlpart/) se hai bisogno di per accedere ai dati XML personalizzati.

### Esempi

Mostra come accedere alla raccolta di parti personalizzate arbitrarie di un documento.

```csharp
Document doc = new Document(MyDir + "Custom parts OOXML package.docx");

Assert.AreEqual(2, doc.PackageCustomParts.Count);

// Clona la seconda parte, quindi aggiungi il clone alla raccolta.
CustomPart clonedPart = doc.PackageCustomParts[1].Clone();
doc.PackageCustomParts.Add(clonedPart);
Assert.AreEqual(3, doc.PackageCustomParts.Count);

// Enumera la raccolta e stampa ogni parte.
using (IEnumerator<CustomPart> enumerator = doc.PackageCustomParts.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Part index {index}:");
        Console.WriteLine($"\tName:\t\t\t\t{enumerator.Current.Name}");
        Console.WriteLine($"\tContent type:\t\t{enumerator.Current.ContentType}");
        Console.WriteLine($"\tRelationship type:\t{enumerator.Current.RelationshipType}");
        Console.WriteLine(enumerator.Current.IsExternal ?
            "\tSourced from outside the document" :
            $"\tStored within the document, length: {enumerator.Current.Data.Length} bytes");
        index++;
    }
}

// Possiamo rimuovere elementi da questa raccolta singolarmente o tutti in una volta.
doc.PackageCustomParts.RemoveAt(2);

Assert.AreEqual(2, doc.PackageCustomParts.Count);

doc.PackageCustomParts.Clear();

Assert.AreEqual(0, doc.PackageCustomParts.Count);
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Markup](../../aspose.words.markup/)
* assemblea [Aspose.Words](../../)


