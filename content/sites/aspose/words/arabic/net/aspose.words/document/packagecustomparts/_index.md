---
title: Document.PackageCustomParts
second_title: Aspose.Words لمراجع .NET API
description: Document ملكية. الحصول على أو تعيين مجموعة الأجزاء المخصصة محتوى عشوائي المرتبطة بحزمة OOXML باستخدام علاقات غير معروفة.
type: docs
weight: 290
url: /ar/net/aspose.words/document/packagecustomparts/
---
## Document.PackageCustomParts property

الحصول على أو تعيين مجموعة الأجزاء المخصصة (محتوى عشوائي) المرتبطة بحزمة OOXML باستخدام "علاقات غير معروفة".

```csharp
public CustomPartCollection PackageCustomParts { get; set; }
```

### ملاحظات

لا تخلط بين هذه الأجزاء المخصصة وبيانات XML المخصصة. إذا كنت بحاجة إلى الوصول إلى أجزاء XML المخصصة ، فاستخدم ملحق[`CustomXmlParts`](../customxmlparts/) منشأه.

تحتوي هذه المجموعة على أجزاء OOXML التي يكون أصلها هو حزمة OOXML وهي أهداف لها "علاقة غير معروفة" . لمزيد من المعلومات ، راجع[`CustomPart`](../../../aspose.words.markup/custompart/).

يقوم Aspose.Words بتحميل وحفظ الأجزاء المخصصة في مستندات OOXML فقط.

لا يمكن أن تكون هذه الخاصية`لا شيء`.

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

* class [CustomPartCollection](../../../aspose.words.markup/custompartcollection/)
* class [Document](../)
* مساحة الاسم [Aspose.Words](../../document/)
* المجسم [Aspose.Words](../../../)


