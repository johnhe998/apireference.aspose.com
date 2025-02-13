---
title: BaseWebExtensionCollection1.GetEnumerator
second_title: Aspose.Words لمراجع .NET API
description: BaseWebExtensionCollection طريقة. إرجاع عداد يمكنه التكرار من خلال مجموعة.
type: docs
weight: 50
url: /ar/net/aspose.words.webextensions/basewebextensioncollection-1/getenumerator/
---
## BaseWebExtensionCollection&lt;T&gt;.GetEnumerator method

إرجاع عداد يمكنه التكرار من خلال مجموعة.

```csharp
public IEnumerator<T> GetEnumerator()
```

### أمثلة

يوضح كيفية العمل مع مجموعة وثيقة من امتدادات الويب.

```csharp
Document doc = new Document(MyDir + "Web extension.docx");

Assert.AreEqual(1, doc.WebExtensionTaskPanes.Count);

// طباعة جميع خصائص امتداد الويب الخاص بالمستند.
WebExtensionPropertyCollection webExtensionPropertyCollection = doc.WebExtensionTaskPanes[0].WebExtension.Properties;
using (IEnumerator<WebExtensionProperty> enumerator = webExtensionPropertyCollection.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        WebExtensionProperty webExtensionProperty = enumerator.Current;
        Console.WriteLine($"Binding name: {webExtensionProperty.Name}; Binding value: {webExtensionProperty.Value}");
    }
}

// إزالة امتداد الويب.
doc.WebExtensionTaskPanes.Remove(0);

Assert.AreEqual(0, doc.WebExtensionTaskPanes.Count);
```

### أنظر أيضا

* class [BaseWebExtensionCollection&lt;T&gt;](../)
* مساحة الاسم [Aspose.Words.WebExtensions](../../basewebextensioncollection-1/)
* المجسم [Aspose.Words](../../../)


