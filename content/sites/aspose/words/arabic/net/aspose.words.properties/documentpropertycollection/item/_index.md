---
title: DocumentPropertyCollection.Item
second_title: Aspose.Words لمراجع .NET API
description: DocumentPropertyCollection ملكية. إرجاع أDocumentProperty الكائن باسم الخاصية .
type: docs
weight: 20
url: /ar/net/aspose.words.properties/documentpropertycollection/item/
---
## DocumentPropertyCollection indexer (1 of 2)

إرجاع أ[`DocumentProperty`](../../documentproperty/) الكائن باسم الخاصية .

```csharp
public virtual DocumentProperty this[string name] { get; }
```

| معامل | وصف |
| --- | --- |
| name | الاسم غير المتحسس لحالة الأحرف للخاصية المراد استردادها. |

### ملاحظات

إرجاع القيمة فارغة إذا لم يتم العثور على خاصية بالاسم المحدد.

### أمثلة

يوضح كيفية إنشاء خاصية مستند مخصصة تحتوي على التاريخ والوقت.

```csharp
Document doc = new Document();

doc.CustomDocumentProperties.Add("AuthorizationDate", DateTime.Now);

Console.WriteLine($"Document authorized on {doc.CustomDocumentProperties["AuthorizationDate"].ToDateTime()}");
```

### أنظر أيضا

* class [DocumentProperty](../../documentproperty/)
* class [DocumentPropertyCollection](../)
* مساحة الاسم [Aspose.Words.Properties](../../documentpropertycollection/)
* المجسم [Aspose.Words](../../../)

---

## DocumentPropertyCollection indexer (2 of 2)

إرجاع أ[`DocumentProperty`](../../documentproperty/) كائن بالفهرس .

```csharp
public DocumentProperty this[int index] { get; }
```

| معامل | وصف |
| --- | --- |
| index | الفهرس الصفري الخاص بامتداد[`DocumentProperty`](../../documentproperty/) لأسترجاع. |

### أمثلة

يوضح كيفية التعامل مع خصائص المستند المخصصة.

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// يحتوي كل مستند على مجموعة من الخصائص المخصصة ، والتي ، مثل الخصائص المضمنة ، هي أزواج مفتاح - قيمة.
// يحتوي المستند على قائمة ثابتة من الخصائص المضمنة. يقوم المستخدم بإنشاء كافة الخصائص المخصصة. 
Assert.AreEqual("Value of custom document property", doc.CustomDocumentProperties["CustomProperty"].ToString());

doc.CustomDocumentProperties.Add("CustomProperty2", "Value of custom document property #2");

Console.WriteLine("Custom Properties:");
foreach (var customDocumentProperty in doc.CustomDocumentProperties)
{
    Console.WriteLine(customDocumentProperty.Name);
    Console.WriteLine($"\tType:\t{customDocumentProperty.Type}");
    Console.WriteLine($"\tValue:\t\"{customDocumentProperty.Value}\"");
}
```

### أنظر أيضا

* class [DocumentProperty](../../documentproperty/)
* class [DocumentPropertyCollection](../)
* مساحة الاسم [Aspose.Words.Properties](../../documentpropertycollection/)
* المجسم [Aspose.Words](../../../)


