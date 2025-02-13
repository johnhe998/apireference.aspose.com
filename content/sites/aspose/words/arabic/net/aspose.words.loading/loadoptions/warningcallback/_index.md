---
title: LoadOptions.WarningCallback
second_title: Aspose.Words لمراجع .NET API
description: LoadOptions ملكية. تم الاستدعاء أثناء عملية التحميل  عند اكتشاف مشكلة قد تؤدي إلى فقدان دقة البيانات أو التنسيق.
type: docs
weight: 170
url: /ar/net/aspose.words.loading/loadoptions/warningcallback/
---
## LoadOptions.WarningCallback property

تم الاستدعاء أثناء عملية التحميل ، عند اكتشاف مشكلة قد تؤدي إلى فقدان دقة البيانات أو التنسيق.

```csharp
public IWarningCallback WarningCallback { get; set; }
```

### أمثلة

يوضح كيفية طباعة وتخزين التحذيرات التي تحدث أثناء تحميل المستند.

```csharp
{
    // إنشاء كائن LoadOptions جديد وتعيين سمة WarningCallback الخاصة به
    // كمثال لتطبيق IWarningCallback الخاص بنا.
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.WarningCallback = new DocumentLoadingWarningCallback();

    // سيطبع رد الاتصال لدينا جميع التحذيرات التي تظهر أثناء عملية التحميل.
    Document doc = new Document(MyDir + "Document.docx", loadOptions);

    List<WarningInfo> warnings = ((DocumentLoadingWarningCallback)loadOptions.WarningCallback).GetWarnings();
    Assert.AreEqual(3, warnings.Count);

/// <summary>
/// IWarningCallback الذي يطبع التحذيرات وتفاصيلها فور ظهورها أثناء تحميل المستند.
/// </summary>
private class DocumentLoadingWarningCallback : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        Console.WriteLine($"Warning: {info.WarningType}");
        Console.WriteLine($"\tSource: {info.Source}");
        Console.WriteLine($"\tDescription: {info.Description}");
        mWarnings.Add(info);
    }

    public List<WarningInfo> GetWarnings()
    {
        return mWarnings;
    }

    private readonly List<WarningInfo> mWarnings = new List<WarningInfo>();
}
```

### أنظر أيضا

* interface [IWarningCallback](../../../aspose.words/iwarningcallback/)
* class [LoadOptions](../)
* مساحة الاسم [Aspose.Words.Loading](../../loadoptions/)
* المجسم [Aspose.Words](../../../)


