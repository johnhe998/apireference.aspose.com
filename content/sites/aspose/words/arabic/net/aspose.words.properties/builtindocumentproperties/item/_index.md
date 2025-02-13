---
title: BuiltInDocumentProperties.Item
second_title: Aspose.Words لمراجع .NET API
description: BuiltInDocumentProperties ملكية. إرجاع أDocumentProperty الكائن باسم الخاصية .
type: docs
weight: 130
url: /ar/net/aspose.words.properties/builtindocumentproperties/item/
---
## BuiltInDocumentProperties indexer

إرجاع أ[`DocumentProperty`](../../documentproperty/) الكائن باسم الخاصية .

```csharp
public override DocumentProperty this[string name] { get; }
```

| معامل | وصف |
| --- | --- |
| name | الاسم غير المتحسس لحالة الأحرف للخاصية المراد استردادها. |

### ملاحظات

تتوافق أسماء سلسلة الخصائص مع أسماء الخصائص typed المتاحة من[`BuiltInDocumentProperties`](../).

إذا طلبت خاصية غير موجودة في المستند ، ولكن تم التعرف على name للخاصية كاسم مضمّن صالح ،[`DocumentProperty`](../../documentproperty/) يتم إنشاؤه وإضافته إلى المجموعة وإعادته. يتم تعيين الخاصية المنشأة حديثًا قيمة افتراضية (سلسلة فارغة ، صفر ، خطأ أو DateTime.MinValue اعتمادًا على type للخاصية المضمنة).

إذا طلبت خاصية غير موجودة في المستند ولم يتم التعرف على name كاسم مضمن ، فسيتم إرجاع قيمة خالية.

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
* class [BuiltInDocumentProperties](../)
* مساحة الاسم [Aspose.Words.Properties](../../builtindocumentproperties/)
* المجسم [Aspose.Words](../../../)


