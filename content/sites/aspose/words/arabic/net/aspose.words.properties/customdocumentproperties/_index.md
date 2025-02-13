---
title: Class CustomDocumentProperties
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Properties.CustomDocumentProperties فصل. مجموعة من خصائص المستند المخصصة.
type: docs
weight: 4210
url: /ar/net/aspose.words.properties/customdocumentproperties/
---
## CustomDocumentProperties class

مجموعة من خصائص المستند المخصصة.

```csharp
public class CustomDocumentProperties : DocumentPropertyCollection
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Count](../../aspose.words.properties/documentpropertycollection/count/) { get; } | الحصول على عدد العناصر في المجموعة. |
| [Item](../../aspose.words.properties/documentpropertycollection/item/) { get; } | إرجاع أ[`DocumentProperty`](../documentproperty/) كائن بالفهرس . |
| virtual [Item](../../aspose.words.properties/documentpropertycollection/item/) { get; } | إرجاع أ[`DocumentProperty`](../documentproperty/) الكائن باسم الخاصية . |

## طُرق

| اسم | وصف |
| --- | --- |
| [Add](../../aspose.words.properties/customdocumentproperties/add/#add)(string, bool) | إنشاء خاصية مستند مخصصة جديدة لملف **نوع الملكية. منطقي** نوع البيانات . |
| [Add](../../aspose.words.properties/customdocumentproperties/add/#add_3)(string, DateTime) | إنشاء خاصية مستند مخصصة جديدة لملف **PropertyType.DateTime** نوع البيانات . |
| [Add](../../aspose.words.properties/customdocumentproperties/add/#add_1)(string, double) | إنشاء خاصية مستند مخصصة جديدة لملف **نوع الملكية** نوع البيانات . |
| [Add](../../aspose.words.properties/customdocumentproperties/add/#add_2)(string, int) | إنشاء خاصية مستند مخصصة جديدة لملف **نوع الملكية** نوع البيانات . |
| [Add](../../aspose.words.properties/customdocumentproperties/add/#add_4)(string, string) | إنشاء خاصية مستند مخصصة جديدة لملف **PropertyType.String** نوع البيانات . |
| [AddLinkToContent](../../aspose.words.properties/customdocumentproperties/addlinktocontent/)(string, string) | إنشاء ارتباط جديد بخاصية مستند مخصص للمحتوى. |
| [Clear](../../aspose.words.properties/documentpropertycollection/clear/)() | يزيل كل الخصائص من المجموعة. |
| [Contains](../../aspose.words.properties/documentpropertycollection/contains/)(string) | إرجاع صحيح في حالة وجود خاصية بالاسم المحدد في المجموعة. |
| [GetEnumerator](../../aspose.words.properties/documentpropertycollection/getenumerator/)() | إرجاع كائن العداد الذي يمكن استخدامه للتكرار على كافة العناصر في المجموعة. |
| [IndexOf](../../aspose.words.properties/documentpropertycollection/indexof/)(string) | الحصول على فهرس الخاصية بالاسم . |
| [Remove](../../aspose.words.properties/documentpropertycollection/remove/)(string) | يزيل خاصية بالاسم المحدد من المجموعة. |
| [RemoveAt](../../aspose.words.properties/documentpropertycollection/removeat/)(int) | يزيل خاصية في الفهرس المحدد . |

### ملاحظات

كل[`DocumentProperty`](../documentproperty/) يمثل الكائن خاصية مخصصة لمستند حاوية.

أسماء الخصائص غير حساسة لحالة الأحرف.

يتم فرز الخصائص في المجموعة أبجديًا حسب الاسم.

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

* class [Document](../../aspose.words/document/)
* property [BuiltInDocumentProperties](../../aspose.words/document/builtindocumentproperties/)
* property [CustomDocumentProperties](../../aspose.words/document/customdocumentproperties/)
* class [DocumentPropertyCollection](../documentpropertycollection/)
* مساحة الاسم [Aspose.Words.Properties](../../aspose.words.properties/)
* المجسم [Aspose.Words](../../)


