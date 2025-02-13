---
title: BaseWebExtensionCollection1.GetEnumerator
second_title: Aspose.Words per .NET API Reference
description: BaseWebExtensionCollection metodo. Restituisce un enumeratore in grado di scorrere una raccolta.
type: docs
weight: 50
url: /it/net/aspose.words.webextensions/basewebextensioncollection-1/getenumerator/
---
## BaseWebExtensionCollection&lt;T&gt;.GetEnumerator method

Restituisce un enumeratore in grado di scorrere una raccolta.

```csharp
public IEnumerator<T> GetEnumerator()
```

### Esempi

Mostra come lavorare con la raccolta di estensioni Web di un documento.

```csharp
Document doc = new Document(MyDir + "Web extension.docx");

Assert.AreEqual(1, doc.WebExtensionTaskPanes.Count);

// Stampa tutte le proprietà dell'estensione web del documento.
WebExtensionPropertyCollection webExtensionPropertyCollection = doc.WebExtensionTaskPanes[0].WebExtension.Properties;
using (IEnumerator<WebExtensionProperty> enumerator = webExtensionPropertyCollection.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        WebExtensionProperty webExtensionProperty = enumerator.Current;
        Console.WriteLine($"Binding name: {webExtensionProperty.Name}; Binding value: {webExtensionProperty.Value}");
    }
}

// Rimuovere l'estensione web.
doc.WebExtensionTaskPanes.Remove(0);

Assert.AreEqual(0, doc.WebExtensionTaskPanes.Count);
```

### Guarda anche

* class [BaseWebExtensionCollection&lt;T&gt;](../)
* spazio dei nomi [Aspose.Words.WebExtensions](../../basewebextensioncollection-1/)
* assemblea [Aspose.Words](../../../)


