---
title: Class CustomPart
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Markup.CustomPart فصل. يمثل جزءًا مخصصًا محتوى عشوائي لم يتم تحديده بواسطة معيار ISO / IEC 29500.
type: docs
weight: 3660
url: /ar/net/aspose.words.markup/custompart/
---
## CustomPart class

يمثل جزءًا مخصصًا (محتوى عشوائي) لم يتم تحديده بواسطة معيار ISO / IEC 29500.

```csharp
public class CustomPart
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [CustomPart](custompart/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [ContentType](../../aspose.words.markup/custompart/contenttype/) { get; set; } | يحدد نوع المحتوى لهذا الجزء المخصص. |
| [Data](../../aspose.words.markup/custompart/data/) { get; set; } | يحتوي على بيانات هذا الجزء المخصص . |
| [IsExternal](../../aspose.words.markup/custompart/isexternal/) { get; set; } | `خطأ شنيع` إذا تم تخزين هذا الجزء المخصص داخل حزمة OOXML.`حقيقي` إذا كان هذا الجزء المخصص هدفًا خارجيًا. |
| [Name](../../aspose.words.markup/custompart/name/) { get; set; } | الحصول على الاسم المطلق لهذا الجزء أو تعيينه داخل حزمة OOXML أو عنوان URL الهدف. |
| [RelationshipType](../../aspose.words.markup/custompart/relationshiptype/) { get; set; } | الحصول على نوع العلاقة أو تعيينه من الجزء الأصل إلى هذا الجزء المخصص. |

## طُرق

| اسم | وصف |
| --- | --- |
| [Clone](../../aspose.words.markup/custompart/clone/)() | عمل نسخة "عميقة بدرجة كافية" من الكائن. لا يكرر بايتات ملف[`Data`](./data/) القيمة . |

### ملاحظات

تمثل هذه الفئة جزء OOXML الذي يعد هدفًا لـ "علاقة غير معروفة". تعتبر جميع العلاقات غير المحددة في ISO / IEC 29500 "علاقات غير معروفة" . العلاقات غير المعروفة مسموح بها ضمن مستند Office Open XML بشرط أن تكون متوافقة إلى إرشادات ترميز العلاقة.

يحتفظ Microsoft Word بالأجزاء المخصصة أثناء دورات الفتح / الحفظ. يمكن العثور على بعض المعلومات الإضافية هنا http://blogs.msdn.com/dmahugh/archive/2006/11/25/arbitrary-content-in-an-opc-package.aspx

Aspose.Words أيضًا رحلات ذهاب وعودة إلى أجزاء مخصصة ، بالإضافة إلى ذلك ، يسمح بالوصول برمجيًا إلى هذه الأجزاء عبر`CustomPart` و[`CustomPartCollection`](../custompartcollection/) أشياء.

لا تخلط بين الأجزاء المخصصة وبيانات XML المخصصة. يستخدم[`CustomXmlPart`](../customxmlpart/) إذا كنت بحاجة إلى للوصول إلى بيانات XML المخصصة.

### أمثلة

يوضح كيفية الوصول إلى مجموعة الأجزاء المخصصة التعسفية للمستند.

```csharp
Document doc = new Document(MyDir + "Custom parts OOXML package.docx");

Assert.AreEqual(2, doc.PackageCustomParts.Count);

// استنساخ الجزء الثاني ، ثم أضف النسخة إلى المجموعة.
CustomPart clonedPart = doc.PackageCustomParts[1].Clone();
doc.PackageCustomParts.Add(clonedPart);
Assert.AreEqual(3, doc.PackageCustomParts.Count);

// تعداد المجموعة وطباعة كل جزء.
using (IEnumerator<CustomPart> enumerator = doc.PackageCustomParts.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Part index {index}:");
        Console.WriteLine($"\tName:\t\t\t\t{enumerator.Current.Name}");
        Console.WriteLine($"\tContent type:\t\t{enumerator.Current.ContentType}");
        Console.WriteLine($"\tRelationship type:\t{enumerator.Current.RelationshipType}");
        Console.WriteLine(enumerator.Current.IsExternal ?
            "\tSourced from outside the document" :
            $"\tStored within the document, length: {enumerator.Current.Data.Length} bytes");
        index++;
    }
}

// يمكننا إزالة العناصر من هذه المجموعة بشكل فردي أو كلها مرة واحدة.
doc.PackageCustomParts.RemoveAt(2);

Assert.AreEqual(2, doc.PackageCustomParts.Count);

doc.PackageCustomParts.Clear();

Assert.AreEqual(0, doc.PackageCustomParts.Count);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Markup](../../aspose.words.markup/)
* المجسم [Aspose.Words](../../)


