---
title: DigitalSignatureCollection.GetEnumerator
second_title: Aspose.Words per .NET API Reference
description: DigitalSignatureCollection metodo. Restituisce un oggetto enumeratore dizionario che può essere utilizzato per scorrere tutti gli elementi della raccolta.
type: docs
weight: 50
url: /it/net/aspose.words.digitalsignatures/digitalsignaturecollection/getenumerator/
---
## DigitalSignatureCollection.GetEnumerator method

Restituisce un oggetto enumeratore dizionario che può essere utilizzato per scorrere tutti gli elementi della raccolta.

```csharp
public IEnumerator<DigitalSignature> GetEnumerator()
```

### Esempi

Mostra come stampare tutte le firme digitali di un documento firmato.

```csharp
DigitalSignatureCollection digitalSignatures =
    DigitalSignatureUtil.LoadSignatures(MyDir + "Digitally signed.docx");

using (IEnumerator<DigitalSignature> enumerator = digitalSignatures.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        DigitalSignature ds = enumerator.Current;

        if (ds != null)
            Console.WriteLine(ds.ToString());
    }
}
```

### Guarda anche

* class [DigitalSignature](../../digitalsignature/)
* class [DigitalSignatureCollection](../)
* spazio dei nomi [Aspose.Words.DigitalSignatures](../../digitalsignaturecollection/)
* assemblea [Aspose.Words](../../../)


