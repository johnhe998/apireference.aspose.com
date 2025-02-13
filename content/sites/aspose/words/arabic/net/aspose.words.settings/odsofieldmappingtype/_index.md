---
title: Enum OdsoFieldMappingType
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Settings.OdsoFieldMappingType تعداد. يحدد الأنواع المحتملة المستخدمة للإشارة إلى ما إذا تم تعيين حقل دمج بريد معين إلى عمود في مصدر البيانات الخارجية المحدد.
type: docs
weight: 5620
url: /ar/net/aspose.words.settings/odsofieldmappingtype/
---
## OdsoFieldMappingType enumeration

يحدد الأنواع المحتملة المستخدمة للإشارة إلى ما إذا تم تعيين حقل دمج بريد معين إلى عمود في مصدر البيانات الخارجية المحدد.

```csharp
public enum OdsoFieldMappingType
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Column | `0` | تحديد أن حقل دمج المراسلات قد تم تعيينه إلى عمود في مصدر البيانات الخارجية المحدد. |
| Null | `1` | تحديد أن حقل دمج المراسلات لم يتم تعيينه لعمود في مصدر البيانات الخارجية المحدد. |
| Default | `1` | يساويNull . |

### أمثلة

يوضح كيفية الوصول إلى مجموعة البيانات التي تعين أعمدة مصدر البيانات لدمج الحقول.

```csharp
Document doc = new Document(MyDir + "Odso data.docx");

// تحدد هذه المجموعة كيف سيقوم دمج البريد بتعيين أعمدة من مصدر بيانات
// إلى حقول MERGEFIELD و ADDRESSBLOCK و GREETINGLINE المحددة مسبقًا.
OdsoFieldMapDataCollection dataCollection = doc.MailMergeSettings.Odso.FieldMapDatas;
Assert.AreEqual(30, dataCollection.Count);

using (IEnumerator<OdsoFieldMapData> enumerator = dataCollection.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Field map data index {index++}, type \"{enumerator.Current.Type}\":");

        Console.WriteLine(
            enumerator.Current.Type != OdsoFieldMappingType.Null
                ? $"\tColumn \"{enumerator.Current.Name}\", number {enumerator.Current.Column} mapped to merge field \"{enumerator.Current.MappedName}\"."
                : "\tNo valid column to field mapping data present.");
    }
}

// استنساخ العناصر في هذه المجموعة.
Assert.AreNotEqual(dataCollection[0], dataCollection[0].Clone());

// استخدم عناصر طريقة "RemoveAt" بشكل فردي عن طريق الفهرس.
dataCollection.RemoveAt(0);

Assert.AreEqual(29, dataCollection.Count);

// استخدم طريقة "المسح" لمسح المجموعة بأكملها مرة واحدة.
dataCollection.Clear();

Assert.AreEqual(0, dataCollection.Count);
```

### أنظر أيضا

* property [Type](../odsofieldmapdata/type/)
* مساحة الاسم [Aspose.Words.Settings](../../aspose.words.settings/)
* المجسم [Aspose.Words](../../)


