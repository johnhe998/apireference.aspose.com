---
title: Class DocumentProperty
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Properties.DocumentProperty فصل. يمثل خاصية مستند مخصصة أو مضمنة.
type: docs
weight: 4220
url: /ar/net/aspose.words.properties/documentproperty/
---
## DocumentProperty class

يمثل خاصية مستند مخصصة أو مضمنة.

```csharp
public class DocumentProperty
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [IsLinkToContent](../../aspose.words.properties/documentproperty/islinktocontent/) { get; } | يوضح ما إذا كانت هذه الخاصية مرتبطة بالمحتوى أم لا. |
| [LinkSource](../../aspose.words.properties/documentproperty/linksource/) { get; } | يحصل على مصدر خاصية الوثيقة المخصصة المرتبطة. |
| [Name](../../aspose.words.properties/documentproperty/name/) { get; } | إرجاع اسم الخاصية. |
| [Type](../../aspose.words.properties/documentproperty/type/) { get; } | الحصول على نوع بيانات الخاصية . |
| [Value](../../aspose.words.properties/documentproperty/value/) { get; set; } | الحصول على أو تحديد قيمة الخاصية. |

## طُرق

| اسم | وصف |
| --- | --- |
| [ToBool](../../aspose.words.properties/documentproperty/tobool/)() | إرجاع قيمة الخاصية على هيئة منطقية. |
| [ToByteArray](../../aspose.words.properties/documentproperty/tobytearray/)() | إرجاع قيمة الخاصية كمصفوفة بايت. |
| [ToDateTime](../../aspose.words.properties/documentproperty/todatetime/)() | إرجاع قيمة الخاصية كـ DateTime بالتوقيت العالمي المنسق. |
| [ToDouble](../../aspose.words.properties/documentproperty/todouble/)() | إرجاع قيمة الخاصية كمضاعفة. |
| [ToInt](../../aspose.words.properties/documentproperty/toint/)() | إرجاع قيمة الخاصية كعدد صحيح. |
| override [ToString](../../aspose.words.properties/documentproperty/tostring/)() | إرجاع قيمة الخاصية كسلسلة منسقة وفقًا للإعدادات المحلية الحالية. |

### أمثلة

يوضح كيفية العمل بخصائص المستند المضمنة.

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// يحتوي كائن "المستند" على بعض بيانات التعريف الخاصة به في أعضائه.
Console.WriteLine($"Document filename:\n\t \"{doc.OriginalFileName}\"");

// يخزن المستند أيضًا البيانات الوصفية في خصائصه المضمنة.
// كل خاصية مضمنة هي عضو في كائن "BuiltInDocumentProperties" للمستند.
Console.WriteLine("Built-in Properties:");
foreach (DocumentProperty docProperty in doc.BuiltInDocumentProperties)
{
    Console.WriteLine(docProperty.Name);
    Console.WriteLine($"\tType:\t{docProperty.Type}");

    // قد تخزن بعض الخصائص قيمًا متعددة.
    if (docProperty.Value is ICollection<object>)
    {
        foreach (object value in docProperty.Value as ICollection<object>)
            Console.WriteLine($"\tValue:\t\"{value}\"");
    }
    else
    {
        Console.WriteLine($"\tValue:\t\"{docProperty.Value}\"");
    }
}
```

### أنظر أيضا

* class [DocumentPropertyCollection](../documentpropertycollection/)
* مساحة الاسم [Aspose.Words.Properties](../../aspose.words.properties/)
* المجسم [Aspose.Words](../../)


