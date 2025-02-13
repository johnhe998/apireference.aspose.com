---
title: Class BaseWebExtensionCollectionT
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.WebExtensions.BaseWebExtensionCollection1T sınıf. için temel sınıfTaskPaneCollection WebExtensionBindingCollection  WebExtensionPropertyCollection veWebExtensionReferenceCollection koleksiyonlar.
type: docs
weight: 6390
url: /tr/net/aspose.words.webextensions/basewebextensioncollection-1/
---
## BaseWebExtensionCollection&lt;T&gt; class

için temel sınıf[`TaskPaneCollection`](../taskpanecollection/) ,[`WebExtensionBindingCollection`](../webextensionbindingcollection/) , [`WebExtensionPropertyCollection`](../webextensionpropertycollection/) ve[`WebExtensionReferenceCollection`](../webextensionreferencecollection/) koleksiyonlar.

```csharp
public abstract class BaseWebExtensionCollection<T> : IEnumerable<T>
    where T : class
```

| Parametre | Tanım |
| --- | --- |
| T | Koleksiyon öğesinin türü. |

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Count](../../aspose.words.webextensions/basewebextensioncollection-1/count/) { get; } | Koleksiyonda bulunan öğelerin sayısını alır. |
| [Item](../../aspose.words.webextensions/basewebextensioncollection-1/item/) { get; set; } | Belirtilen dizindeki bir öğeyi alır veya ayarlar. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [Add](../../aspose.words.webextensions/basewebextensioncollection-1/add/)(T) | Belirtilen öğeyi koleksiyona ekler. |
| [Clear](../../aspose.words.webextensions/basewebextensioncollection-1/clear/)() | Koleksiyondaki tüm öğeleri kaldırır. |
| [GetEnumerator](../../aspose.words.webextensions/basewebextensioncollection-1/getenumerator/)() | Bir koleksiyon boyunca yinelenebilen bir Numaralandırıcı döndürür. |
| [Remove](../../aspose.words.webextensions/basewebextensioncollection-1/remove/)(int) | Belirtilen dizindeki öğeyi koleksiyondan kaldırır. |

### Örnekler

Bir belgenin web uzantıları koleksiyonuyla nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Web extension.docx");

Assert.AreEqual(1, doc.WebExtensionTaskPanes.Count);

// Belgenin web uzantısının tüm özelliklerini yazdırın.
WebExtensionPropertyCollection webExtensionPropertyCollection = doc.WebExtensionTaskPanes[0].WebExtension.Properties;
using (IEnumerator<WebExtensionProperty> enumerator = webExtensionPropertyCollection.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        WebExtensionProperty webExtensionProperty = enumerator.Current;
        Console.WriteLine($"Binding name: {webExtensionProperty.Name}; Binding value: {webExtensionProperty.Value}");
    }
}

// Web uzantısını kaldırın.
doc.WebExtensionTaskPanes.Remove(0);

Assert.AreEqual(0, doc.WebExtensionTaskPanes.Count);
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.WebExtensions](../../aspose.words.webextensions/)
* toplantı [Aspose.Words](../../)


