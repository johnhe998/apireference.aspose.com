---
title: BaseWebExtensionCollection1.Count
second_title: Aspose.Words لمراجع .NET API
description: BaseWebExtensionCollection ملكية. الحصول على عدد العناصر الموجودة في المجموعة.
type: docs
weight: 10
url: /ar/net/aspose.words.webextensions/basewebextensioncollection-1/count/
---
## BaseWebExtensionCollection&lt;T&gt;.Count property

الحصول على عدد العناصر الموجودة في المجموعة.

```csharp
public int Count { get; }
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


