---
title: DocumentBase.WarningCallback
second_title: Aspose.Words لمراجع .NET API
description: DocumentBase ملكية. يتم استدعاؤه أثناء إجراءات معالجة المستندات المختلفة عند اكتشاف مشكلة قد تؤدي إلى في البيانات أو فقدان الدقة في التنسيق .
type: docs
weight: 90
url: /ar/net/aspose.words/documentbase/warningcallback/
---
## DocumentBase.WarningCallback property

يتم استدعاؤه أثناء إجراءات معالجة المستندات المختلفة عند اكتشاف مشكلة قد تؤدي إلى في البيانات أو فقدان الدقة في التنسيق .

```csharp
public IWarningCallback WarningCallback { get; set; }
```

### ملاحظات

قد يصدر المستند تحذيرات في أي مرحلة من مراحل وجوده ، لذلك من المهم إعداد رد اتصال تحذير as مبكرًا قدر الإمكان لتجنب فقد التحذيرات. على سبيل المثال خصائص مثل[`PageCount`](../../document/pagecount/) في الواقع قم ببناء تخطيط المستند الذي يتم استخدامه لاحقًا للعرض ، وقد يتم فقد تحذيرات التخطيط إذا تم تحديد رد الاتصال التحذيري فقط لمكالمات العرض لاحقًا.

### أمثلة

يوضح كيفية استخدام واجهة IWarningCallback لمراقبة تحذيرات استبدال الخط.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Font.Name = "Times New Roman";
    builder.Writeln("Hello world!");

    FontSubstitutionWarningCollector callback = new FontSubstitutionWarningCollector();
    doc.WarningCallback = callback;

    // قم بتخزين المجموعة الحالية من مصادر الخطوط ، والتي ستكون مصدر الخط الافتراضي لكل مستند
    // التي لم نحدد مصدر خط مختلف لها.
    FontSourceBase[] originalFontSources = FontSettings.DefaultInstance.GetFontsSources();

    // لأغراض الاختبار ، سنقوم بتعيين Aspose.Words للبحث عن الخطوط فقط في مجلد غير موجود.
    FontSettings.DefaultInstance.SetFontsFolder(string.Empty, false);

    // عند تقديم المستند ، لن يكون هناك مكان للعثور على الخط "Times New Roman".
    // سيؤدي هذا إلى تحذير بشأن استبدال الخط ، والذي سيكتشفه رد الاتصال الخاص بنا.
    doc.Save(ArtifactsDir + "FontSettings.SubstitutionWarning.pdf");

    FontSettings.DefaultInstance.SetFontsSources(originalFontSources);

    Assert.True(callback.FontSubstitutionWarnings[0].Description
        .Equals(
            "Font 'Times New Roman' has not been found. Using 'Fanwood' font instead. Reason: first available font."));
}

private class FontSubstitutionWarningCollector : IWarningCallback
{
    /// <summary>
    /// يتم الاتصال به في كل مرة يظهر فيها تحذير أثناء التحميل / الحفظ.
    /// </summary>
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontSubstitutionWarnings.Warning(info);
    }

    public WarningInfoCollection FontSubstitutionWarnings = new WarningInfoCollection();
}
```

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

* interface [IWarningCallback](../../iwarningcallback/)
* class [DocumentBase](../)
* مساحة الاسم [Aspose.Words](../../documentbase/)
* المجسم [Aspose.Words](../../../)


