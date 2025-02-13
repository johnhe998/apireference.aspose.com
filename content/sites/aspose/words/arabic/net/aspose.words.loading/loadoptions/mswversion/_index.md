---
title: LoadOptions.MswVersion
second_title: Aspose.Words لمراجع .NET API
description: LoadOptions ملكية. يسمح بتحديد أن عملية تحميل المستند يجب أن تتطابق مع إصدار MS Word محدد. القيمة الافتراضية هيWord2019
type: docs
weight: 100
url: /ar/net/aspose.words.loading/loadoptions/mswversion/
---
## LoadOptions.MswVersion property

يسمح بتحديد أن عملية تحميل المستند يجب أن تتطابق مع إصدار MS Word محدد. القيمة الافتراضية هيWord2019

```csharp
public MsWordVersion MswVersion { get; set; }
```

### ملاحظات

قد تتعامل إصدارات Word المختلفة مع جوانب معينة من محتوى المستند والتنسيق بشكل مختلف قليلاً أثناء عملية التحميل ، مما قد يؤدي إلى اختلافات طفيفة في نموذج كائن المستند.

### أمثلة

يوضح كيفية محاكاة إجراء التحميل لإصدار معين من Microsoft Word أثناء تحميل المستند.

```csharp
// بشكل افتراضي ، تقوم Aspose.Words بتحميل المستندات وفقًا لمواصفات Microsoft Word 2019.
LoadOptions loadOptions = new LoadOptions();

Assert.AreEqual(MsWordVersion.Word2019, loadOptions.MswVersion);

// يفتقد هذا المستند إلى نمط تنسيق الفقرة الافتراضي.
// سيتم إعادة إنشاء هذا النمط الافتراضي عندما نقوم بتحميل المستند إما باستخدام Microsoft Word أو Aspose.Words.
loadOptions.MswVersion = MsWordVersion.Word2007;
Document doc = new Document(MyDir + "Document.docx", loadOptions);

// سيكون لتباعد أسطر النمط هذه القيمة عند تحميله بواسطة مواصفات Microsoft Word 2007.
Assert.AreEqual(12.95d, doc.Styles.DefaultParagraphFormat.LineSpacing, 0.01d);
```

### أنظر أيضا

* enum [MsWordVersion](../../../aspose.words.settings/mswordversion/)
* class [LoadOptions](../)
* مساحة الاسم [Aspose.Words.Loading](../../loadoptions/)
* المجسم [Aspose.Words](../../../)


