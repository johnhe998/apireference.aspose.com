---
title: MetafileRenderingOptions.EmulateRasterOperations
second_title: Aspose.Words لمراجع .NET API
description: MetafileRenderingOptions ملكية. الحصول على أو تعيين قيمة تحدد ما إذا كان يجب محاكاة عمليات البيانات النقطية أم لا.
type: docs
weight: 30
url: /ar/net/aspose.words.saving/metafilerenderingoptions/emulaterasteroperations/
---
## MetafileRenderingOptions.EmulateRasterOperations property

الحصول على أو تعيين قيمة تحدد ما إذا كان يجب محاكاة عمليات البيانات النقطية أم لا.

```csharp
public bool EmulateRasterOperations { get; set; }
```

### ملاحظات

يمكن استخدام عمليات البيانات النقطية المحددة في ملفات التعريف. لا يمكن تقديمها مباشرة إلى الرسومات المتجهة. تتطلب محاكاة العمليات النقطية تنقيطًا جزئيًا للرسومات المتجهة الناتجة والتي قد تؤثر على أداء عرض ملف التعريف .

عندما يتم تعيين هذه القيمة على`حقيقي`، Aspose.Words يحاكي العمليات النقطية. قد يكون الناتج الناتج نقطيًا جزئيًا وقد يكون الأداء أبطأ.

عندما يتم تعيين هذه القيمة على`خاطئة`، Aspose.Words لا تحاكي العمليات النقطية. عندما تواجه Aspose.Words عملية نقطية في ملف تعريف ، فإنها ترجع إلى تحويل ملف التعريف إلى صورة نقطية باستخدام نظام التشغيل .

يتم استخدام هذا الخيار فقط عندما يتم تقديم ملف التعريف كرسومات متجهة.

النظام الأساسي`حقيقي`.

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

* class [MetafileRenderingOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../metafilerenderingoptions/)
* المجسم [Aspose.Words](../../../)


