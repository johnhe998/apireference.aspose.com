---
title: PageSetup.FirstPageTray
second_title: Aspose.Words لمراجع .NET API
description: PageSetup ملكية. الحصول على أو تعيين علبة الورق حاوية لاستخدامها في الصفحة الأولى من القسم . القيمة هي التنفيذ الطابعة الخاصة.
type: docs
weight: 130
url: /ar/net/aspose.words/pagesetup/firstpagetray/
---
## PageSetup.FirstPageTray property

الحصول على أو تعيين علبة الورق (حاوية) لاستخدامها في الصفحة الأولى من القسم . القيمة هي التنفيذ (الطابعة) الخاصة.

```csharp
public int FirstPageTray { get; set; }
```

### أمثلة

يوضح كيفية الحصول على جميع الأقسام في مستند ما لاستخدام درج الورق الافتراضي للطابعة المحددة.

```csharp
Document doc = new Document();

// ابحث عن الطابعة الافتراضية التي سنستخدمها لطباعة هذا المستند.
// يمكنك تحديد طابعة معينة باستخدام خاصية "اسم الطابعة" الخاصة بالكائن PrinterSettings.
PrinterSettings settings = new PrinterSettings();

// قيمة درج الورق المخزنة في المستندات خاصة بالطابعة.
// هذا يعني أن الكود أدناه يعيد تعيين جميع قيم علبة الصفحة لاستخدام الدرج الافتراضي الحالي للطابعات.
// يمكنك تعداد PrinterSettings.PaperSources للعثور على قيم علبة الورق الصالحة الأخرى للطابعة المحددة.
foreach (Section section in doc.Sections.OfType<Section>())
{
    section.PageSetup.FirstPageTray = settings.DefaultPageSettings.PaperSource.RawKind;
    section.PageSetup.OtherPagesTray = settings.DefaultPageSettings.PaperSource.RawKind;
}
```

يوضح كيفية إعداد الطباعة باستخدام أدراج طابعة مختلفة لأحجام ورق مختلفة.

```csharp
Document doc = new Document();

// ابحث عن الطابعة الافتراضية التي سنستخدمها لطباعة هذا المستند.
// يمكنك تحديد طابعة معينة باستخدام خاصية "اسم الطابعة" الخاصة بالكائن PrinterSettings.
PrinterSettings settings = new PrinterSettings();

// هذا هو الدرج الذي سنستخدمه للصفحات بحجم الورق "A4".
int printerTrayForA4 = settings.PaperSources[0].RawKind;

// هذا هو الدرج الذي سنستخدمه للصفحات بحجم ورق "Letter".
int printerTrayForLetter = settings.PaperSources[1].RawKind;

// قم بتعديل كائن PageSettings في هذا القسم للحصول على Microsoft Word لتوجيه الطابعة
// لاستخدام أحد الأدراج التي حددناها أعلاه ، اعتمادًا على حجم الورق في هذا القسم.
foreach (Section section in doc.Sections.OfType<Section>())
{
    if (section.PageSetup.PaperSize == Aspose.Words.PaperSize.Letter)
    {
        section.PageSetup.FirstPageTray = printerTrayForLetter;
        section.PageSetup.OtherPagesTray = printerTrayForLetter;
    }
    else if (section.PageSetup.PaperSize == Aspose.Words.PaperSize.A4)
    {
        section.PageSetup.FirstPageTray = printerTrayForA4;
        section.PageSetup.OtherPagesTray = printerTrayForA4;
    }
}
```

### أنظر أيضا

* class [PageSetup](../)
* مساحة الاسم [Aspose.Words](../../pagesetup/)
* المجسم [Aspose.Words](../../../)


