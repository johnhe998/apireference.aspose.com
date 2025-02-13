---
title: Class BaseWebExtensionCollectionT
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.WebExtensions.BaseWebExtensionCollection1T فصل. الفئة الأساسية لـTaskPaneCollection وWebExtensionBindingCollection  WebExtensionPropertyCollection وWebExtensionReferenceCollection المجموعات.
type: docs
weight: 6390
url: /ar/net/aspose.words.webextensions/basewebextensioncollection-1/
---
## BaseWebExtensionCollection&lt;T&gt; class

الفئة الأساسية لـ[`TaskPaneCollection`](../taskpanecollection/) و[`WebExtensionBindingCollection`](../webextensionbindingcollection/) ، [`WebExtensionPropertyCollection`](../webextensionpropertycollection/) و[`WebExtensionReferenceCollection`](../webextensionreferencecollection/) المجموعات.

```csharp
public abstract class BaseWebExtensionCollection<T> : IEnumerable<T>
    where T : class
```

| معامل | وصف |
| --- | --- |
| T | نوع عنصر المجموعة. |

## الخصائص

| اسم | وصف |
| --- | --- |
| [Count](../../aspose.words.webextensions/basewebextensioncollection-1/count/) { get; } | الحصول على عدد العناصر الموجودة في المجموعة. |
| [Item](../../aspose.words.webextensions/basewebextensioncollection-1/item/) { get; set; } | الحصول على أو تعيين عنصر في الفهرس المحدد. |

## طُرق

| اسم | وصف |
| --- | --- |
| [Add](../../aspose.words.webextensions/basewebextensioncollection-1/add/)(T) | يضيف عنصرًا محددًا إلى المجموعة. |
| [Clear](../../aspose.words.webextensions/basewebextensioncollection-1/clear/)() | يزيل كل العناصر من المجموعة. |
| [GetEnumerator](../../aspose.words.webextensions/basewebextensioncollection-1/getenumerator/)() | إرجاع عداد يمكنه التكرار من خلال مجموعة. |
| [Remove](../../aspose.words.webextensions/basewebextensioncollection-1/remove/)(int) | يزيل العنصر في الفهرس المحدد من المجموعة. |

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

* مساحة الاسم [Aspose.Words.WebExtensions](../../aspose.words.webextensions/)
* المجسم [Aspose.Words](../../)


