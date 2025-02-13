---
title: Enum WarningType
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.WarningType تعداد. يحدد نوع التحذير الذي تم إصداره بواسطة Aspose.Words أثناء تحميل المستندات أو حفظها.
type: docs
weight: 6350
url: /ar/net/aspose.words/warningtype/
---
## WarningType enumeration

يحدد نوع التحذير الذي تم إصداره بواسطة Aspose.Words أثناء تحميل المستندات أو حفظها.

```csharp
[Flags]
public enum WarningType
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| DataLossCategory | `FF` | ستفقد بعض النصوص / char / الصورة أو البيانات الأخرى من شجرة المستند بعد التحميل ، أو من المستند الذي تم إنشاؤه بعد الحفظ . |
| DataLoss | `1` | فقدان بيانات عام ، بدون رمز محدد . |
| MajorFormattingLossCategory | `FF00` | قد يبدو المستند الناتج أو مكان معين فيه مختلفًا إلى حد كبير مقارنة بالمستند الأصلي. |
| MajorFormattingLoss | `100` | فقدان التنسيق الرئيسي العام ، بدون رمز محدد. |
| MinorFormattingLossCategory | `FF0000` | قد يبدو المستند الناتج أو موقعًا معينًا مختلفًا بعض الشيء مقارنة بالمستند الأصلي. |
| MinorFormattingLoss | `10000` | فقدان التنسيق البسيط العام ، بدون رمز محدد. |
| FontSubstitution | `20000` | تم استبدال الخط. |
| FontEmbedding | `40000` | فقدان معلومات الخط المضمنة أثناء حفظ المستند. |
| UnexpectedContentCategory | `F000000` | تعذر التعرف على بعض المحتويات في المستند المصدر (أي غير مدعوم) ، وقد يتسبب هذا أو لا في حدوث مشكلات أو يؤدي إلى فقدان البيانات / التنسيق. |
| UnexpectedContent | `1000000` | محتوى عام غير متوقع ، بدون رمز محدد. |
| Hint | `10000000` | تنصح بمشكلة محتملة أو تقترح تحسينًا . |

### أمثلة

يوضح كيفية تعيين الخاصية للعثور على أقرب تطابق لخط مفقود من مصادر الخط المتاحة.

```csharp
[Test]
public void EnableFontSubstitution()
{
    // افتح مستندًا يحتوي على نص منسق بخط غير موجود في أي من مصادر الخطوط لدينا.
    Document doc = new Document(MyDir + "Missing font.docx");

    // تعيين رد اتصال للتعامل مع تحذيرات استبدال الخط.
    HandleDocumentSubstitutionWarnings substitutionWarningHandler = new HandleDocumentSubstitutionWarnings();
    doc.WarningCallback = substitutionWarningHandler;

    // تعيين اسم الخط الافتراضي وتمكين استبدال الخط.
    FontSettings fontSettings = new FontSettings();
    fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
    ;
    fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = true;

    // سنحصل على تحذير بشأن استبدال الخط إذا حفظنا مستندًا بخط مفقود.
    doc.FontSettings = fontSettings;
    doc.Save(ArtifactsDir + "FontSettings.EnableFontSubstitution.pdf");

    using (IEnumerator<WarningInfo> warnings = substitutionWarningHandler.FontWarnings.GetEnumerator())
        while (warnings.MoveNext())
            Console.WriteLine(warnings.Current.Description);

    // يمكننا أيضًا التحقق من التحذيرات في المجموعة ومسحها.
    Assert.AreEqual(WarningSource.Layout, substitutionWarningHandler.FontWarnings[0].Source);
    Assert.AreEqual(
        "Font '28 Days Later' has not been found. Using 'Calibri' font instead. Reason: alternative name from document.",
        substitutionWarningHandler.FontWarnings[0].Description);

    substitutionWarningHandler.FontWarnings.Clear();

    Assert.That(substitutionWarningHandler.FontWarnings, Is.Empty);
}

public class HandleDocumentSubstitutionWarnings : IWarningCallback
{
    /// <summary>
    /// يتم الاتصال به في كل مرة يظهر فيها تحذير أثناء التحميل / الحفظ.
    /// </summary>
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


