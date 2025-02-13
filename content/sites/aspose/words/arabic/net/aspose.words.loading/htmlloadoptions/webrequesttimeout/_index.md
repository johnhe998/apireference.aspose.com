---
title: HtmlLoadOptions.WebRequestTimeout
second_title: Aspose.Words لمراجع .NET API
description: HtmlLoadOptions ملكية. عدد المللي ثانية المطلوب انتظاره قبل انتهاء مهلة طلب الويب. القيمة الافتراضية هي 100000 مللي ثانية 100 ثانية .
type: docs
weight: 70
url: /ar/net/aspose.words.loading/htmlloadoptions/webrequesttimeout/
---
## HtmlLoadOptions.WebRequestTimeout property

عدد المللي ثانية المطلوب انتظاره قبل انتهاء مهلة طلب الويب. القيمة الافتراضية هي 100000 مللي ثانية (100 ثانية) .

```csharp
public int WebRequestTimeout { get; set; }
```

### ملاحظات

عدد المللي ثانية الذي ينتظره Aspose.Words استجابة ، عند تحميل موارد خارجية (صور ، style أوراق) مرتبطة بمستندات HTML و MHTML .

### أمثلة

يوضح كيفية تعيين حد زمني لطلبات الويب عند تحميل مستند بموارد خارجية مرتبطة بعناوين URL.

```csharp
{
    // قم بإنشاء كائن HtmlLoadOptions جديد وتحقق من حد انتهاء المهلة لطلب الويب.
    HtmlLoadOptions options = new HtmlLoadOptions();

    // عند تحميل مستند Html بموارد مرتبطة خارجيًا بعنوان URL لعنوان الويب ،
    // Aspose.Words ستجهض طلبات الويب التي تفشل في جلب الموارد خلال هذا الحد الزمني ، بالمللي ثانية.
    Assert.AreEqual(100000, options.WebRequestTimeout);

    // قم بتعيين WarningCallback يسجل جميع التحذيرات التي تحدث أثناء التحميل.
    ListDocumentWarnings warningCallback = new ListDocumentWarnings();
    options.WarningCallback = warningCallback;

    // قم بتحميل مثل هذا المستند وتحقق من إنشاء شكل ببيانات الصورة.
    // ستتطلب هذه الصورة المرتبطة تحميل طلب ويب ، والذي سيتعين إكماله في غضون الوقت المحدد لدينا.
    string html = $@"
        <html>
            <img src=""{ImageUrl}"" alt=""Aspose logo"" style=""width:400px;height:400px;"">
        </html>
    ";

    // قم بتعيين حد غير معقول للمهلة وحاول تحميل المستند مرة أخرى.
    options.WebRequestTimeout = 0;
    Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), options);
    Assert.AreEqual(2, warningCallback.Warnings().Count);

    // طلب الويب الذي يفشل في الحصول على صورة خلال المهلة الزمنية المحددة سيستمر في إنتاج صورة.
    // ومع ذلك ، ستكون الصورة باللون الأحمر "x" التي تشير عادةً إلى الصور المفقودة.
    Shape imageShape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
    Assert.AreEqual(924, imageShape.ImageData.ImageBytes.Length);

    // يمكننا أيضًا تكوين رد اتصال مخصص لالتقاط أي تحذيرات من طلبات الويب التي انتهت مهلتها.
    Assert.AreEqual(WarningSource.Html, warningCallback.Warnings()[0].Source);
    Assert.AreEqual(WarningType.DataLoss, warningCallback.Warnings()[0].WarningType);
    Assert.AreEqual($"Couldn't load a resource from \'{ImageUrl}\'.", warningCallback.Warnings()[0].Description);

    Assert.AreEqual(WarningSource.Html, warningCallback.Warnings()[1].Source);
    Assert.AreEqual(WarningType.DataLoss, warningCallback.Warnings()[1].WarningType);
    Assert.AreEqual("Image has been replaced with a placeholder.", warningCallback.Warnings()[1].Description);

    doc.Save(ArtifactsDir + "HtmlLoadOptions.WebRequestTimeout.docx");
}

/// <summary>
/// يخزن جميع التحذيرات التي تحدث أثناء عملية تحميل المستند في قائمة.
/// </summary>
private class ListDocumentWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        mWarnings.Add(info);
    }

    public List<WarningInfo> Warnings() { 
        return mWarnings;
    }

    private readonly List<WarningInfo> mWarnings = new List<WarningInfo>();
}
```

### أنظر أيضا

* class [HtmlLoadOptions](../)
* مساحة الاسم [Aspose.Words.Loading](../../htmlloadoptions/)
* المجسم [Aspose.Words](../../../)


