---
title: BaseWebExtensionCollection1.Item
second_title: Référence de l'API Aspose.Words pour .NET
description: BaseWebExtensionCollection propriété. Obtient ou définit un élément à lindex spécifié.
type: docs
weight: 20
url: /fr/net/aspose.words.webextensions/basewebextensioncollection-1/item/
---
## BaseWebExtensionCollection&lt;T&gt; indexer

Obtient ou définit un élément à l'index spécifié.

```csharp
public T this[int index] { get; set; }
```

| Paramètre | La description |
| --- | --- |
| index | Index de base zéro de l'élément. |

### Exemples

Montre comment utiliser la collection d'extensions Web d'un document.

```csharp
Document doc = new Document(MyDir + "Web extension.docx");

Assert.AreEqual(1, doc.WebExtensionTaskPanes.Count);

// Affiche toutes les propriétés de l'extension Web du document.
WebExtensionPropertyCollection webExtensionPropertyCollection = doc.WebExtensionTaskPanes[0].WebExtension.Properties;
using (IEnumerator<WebExtensionProperty> enumerator = webExtensionPropertyCollection.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        WebExtensionProperty webExtensionProperty = enumerator.Current;
        Console.WriteLine($"Binding name: {webExtensionProperty.Name}; Binding value: {webExtensionProperty.Value}");
    }
}

// Supprimer l'extension Web.
doc.WebExtensionTaskPanes.Remove(0);

Assert.AreEqual(0, doc.WebExtensionTaskPanes.Count);
```

### Voir également

* class [BaseWebExtensionCollection&lt;T&gt;](../)
* espace de noms [Aspose.Words.WebExtensions](../../basewebextensioncollection-1/)
* Assemblée [Aspose.Words](../../../)


