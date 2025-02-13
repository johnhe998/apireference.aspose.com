---
title: MetafileRenderingOptions.RenderingMode
second_title: Aspose.Words لمراجع .NET API
description: MetafileRenderingOptions ملكية. الحصول على أو تعيين قيمة تحدد كيفية عرض صور ملف التعريف .
type: docs
weight: 40
url: /ar/net/aspose.words.saving/metafilerenderingoptions/renderingmode/
---
## MetafileRenderingOptions.RenderingMode property

الحصول على أو تعيين قيمة تحدد كيفية عرض صور ملف التعريف .

```csharp
public MetafileRenderingMode RenderingMode { get; set; }
```

### ملاحظات

تعتمد القيمة الافتراضية على تنسيق الحفظ. للصور هو عليهBitmap . بالنسبة إلى التنسيقات الأخرى فهو كذلكVectorWithFallback.

### أمثلة

أضافت العروض رجوعًا إلى عرض الصور النقطية وتغيير نوع التحذيرات حول سجلات ملفات التعريف غير المدعومة.

```csharp
{
    Document doc = new Document(MyDir + "WMF with image.docx");

    MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions();

    // قم بتعيين خاصية "EmulateRasterOperations" على "false" للرجوع إلى الصورة النقطية عندما
    // يواجه ملف تعريف ، والذي سيتطلب عمليات نقطية لتقديمه في ملف PDF الناتج.
    metafileRenderingOptions.EmulateRasterOperations = false;

    // عيّن خاصية "RenderingMode" على "VectorWithFallback" لمحاولة تقديم كل ملف تعريف باستخدام رسومات متجهة.
    metafileRenderingOptions.RenderingMode = MetafileRenderingMode.VectorWithFallback;

    // قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
    // لتعديل كيفية تحويل هذه الطريقة للمستند إلى .PDF وتطبيق التكوين
    // في كائن MetafileRenderingOptions الخاص بنا إلى عملية الحفظ.
    PdfSaveOptions saveOptions = new PdfSaveOptions();
    saveOptions.MetafileRenderingOptions = metafileRenderingOptions;

    HandleDocumentWarnings callback = new HandleDocumentWarnings();
    doc.WarningCallback = callback;

    doc.Save(ArtifactsDir + "PdfSaveOptions.HandleBinaryRasterWarnings.pdf", saveOptions);

    Assert.AreEqual(1, callback.Warnings.Count);
    Assert.AreEqual("'R2_XORPEN' binary raster operation is partly supported.",
        callback.Warnings[0].Description);
}

/// <summary>
/// يطبع ويجمع التحذيرات المتعلقة بضياع التنسيق التي تحدث عند حفظ مستند.
/// </summary>
public class HandleDocumentWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.MinorFormattingLoss)
        {
            Console.WriteLine("Unsupported operation: " + info.Description);
            Warnings.Warning(info);
        }
    }

    public WarningInfoCollection Warnings = new WarningInfoCollection();
}
```

### أنظر أيضا

* enum [MetafileRenderingMode](../../metafilerenderingmode/)
* class [MetafileRenderingOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../metafilerenderingoptions/)
* المجسم [Aspose.Words](../../../)


