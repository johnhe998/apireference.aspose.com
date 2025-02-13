---
title: DigitalSignatureCollection.GetEnumerator
second_title: Referencia de API de Aspose.Words para .NET
description: DigitalSignatureCollection método. Devuelve un objeto de enumerador de diccionario que se puede usar para iterar sobre todos los elementos de la colección.
type: docs
weight: 50
url: /es/net/aspose.words.digitalsignatures/digitalsignaturecollection/getenumerator/
---
## DigitalSignatureCollection.GetEnumerator method

Devuelve un objeto de enumerador de diccionario que se puede usar para iterar sobre todos los elementos de la colección.

```csharp
public IEnumerator<DigitalSignature> GetEnumerator()
```

### Ejemplos

Muestra cómo imprimir todas las firmas digitales de un documento firmado.

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

### Ver también

* class [DigitalSignature](../../digitalsignature/)
* class [DigitalSignatureCollection](../)
* espacio de nombres [Aspose.Words.DigitalSignatures](../../digitalsignaturecollection/)
* asamblea [Aspose.Words](../../../)


