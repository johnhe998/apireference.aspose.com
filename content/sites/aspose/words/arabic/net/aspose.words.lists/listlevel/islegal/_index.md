---
title: ListLevel.IsLegal
second_title: Aspose.Words لمراجع .NET API
description: ListLevel ملكية. صحيح إذا قام المستوى بتحويل جميع الأرقام الموروثة إلى اللغة العربية  خطأ إذا احتفظ بنمط الأرقام .
type: docs
weight: 50
url: /ar/net/aspose.words.lists/listlevel/islegal/
---
## ListLevel.IsLegal property

صحيح إذا قام المستوى بتحويل جميع الأرقام الموروثة إلى اللغة العربية ، خطأ إذا احتفظ بنمط الأرقام .

```csharp
public bool IsLegal { get; set; }
```

### أمثلة

يعرض طرقًا متقدمة لتخصيص تسميات القائمة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// تسمح لنا القائمة بتنظيم وتزيين مجموعات من الفقرات برموز بادئة ومسافات بادئة.
// يمكننا إنشاء قوائم متداخلة عن طريق زيادة مستوى المسافة البادئة. 
// يمكننا بدء قائمة وإنهائها باستخدام خاصية "تنسيق القائمة" الخاصة بمنشئ المستندات. 
// كل فقرة نضيفها بين بداية القائمة ونهايتها ستصبح عنصرًا في القائمة.
List list = doc.Lists.Add(ListTemplate.NumberDefault);

// سيتم تنسيق تسميات المستوى 1 وفقًا لنمط الفقرة "العنوان 1" وستكون لها بادئة.
// ستبدو مثل "الملحق أ" ، "الملحق ب" ...
list.ListLevels[0].NumberFormat = "Appendix \x0000";
list.ListLevels[0].NumberStyle = NumberStyle.UppercaseLetter;
list.ListLevels[0].LinkedStyle = doc.Styles["Heading 1"];

// ستعرض تسميات المستوى 2 الأرقام الحالية لمستويي القائمة الأول والثاني وتحتوي على أصفار بادئة.
// إذا كان مستوى القائمة الأول عند 1 ، فستظهر تسميات القائمة من هذه مثل "القسم (1.01)" ، "القسم (1.02)" ...
list.ListLevels[1].NumberFormat = "Section (\x0000.\x0001)";
list.ListLevels[1].NumberStyle = NumberStyle.LeadingZero;

// لاحظ أن المستوى الأعلى يستخدم ترقيم الأحرف الكبيرة.
// يمكننا تعيين خاصية "IsLegal" لاستخدام الأرقام العربية لمستويات القائمة الأعلى.
list.ListLevels[1].IsLegal = true;
list.ListLevels[1].RestartAfterLevel = 0;

// ستكون تسميات المستوى 3 عبارة عن أرقام رومانية كبيرة مع بادئة ولاحقة وستتم إعادة تشغيلها عند كل عنصر من عناصر القائمة 1.
// ستظهر تسميات القائمة هذه بالشكل "-I-" ، "-II -" ...
list.ListLevels[2].NumberFormat = "-\x0002-";
list.ListLevels[2].NumberStyle = NumberStyle.UppercaseRoman;
list.ListLevels[2].RestartAfterLevel = 1;

// اجعل تسميات جميع مستويات القائمة غامقة.
foreach (ListLevel level in list.ListLevels)
    level.Font.Bold = true;

// تطبيق تنسيق القائمة على الفقرة الحالية.
builder.ListFormat.List = list;

// أنشئ عناصر قائمة تعرض جميع مستويات قائمتنا الثلاثة.
for (int n = 0; n < 2; n++)
{
    for (int i = 0; i < 3; i++)
    {
        builder.ListFormat.ListLevelNumber = i;
        builder.Writeln("Level " + i);
    }
}

builder.ListFormat.RemoveNumbers();

doc.Save(ArtifactsDir + "Lists.CreateListRestartAfterHigher.docx");
```

### أنظر أيضا

* class [ListLevel](../)
* مساحة الاسم [Aspose.Words.Lists](../../listlevel/)
* المجسم [Aspose.Words](../../../)


