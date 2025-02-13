---
title: Enum MetafileRenderingMode
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.MetafileRenderingMode تعداد. يحدد كيف يجب على Aspose.Words عرض ملفات تعريف WMF و EMF .
type: docs
weight: 5010
url: /ar/net/aspose.words.saving/metafilerenderingmode/
---
## MetafileRenderingMode enumeration

يحدد كيف يجب على Aspose.Words عرض ملفات تعريف WMF و EMF .

```csharp
public enum MetafileRenderingMode
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| VectorWithFallback | `0` | Aspose.Words يحاول تقديم ملف تعريف كرسومات متجهة. إذا تعذر على Aspose.Words عرض بعض تسجيلات ملف التعريف بشكل صحيح إلى رسومات متجهة ، فإن Aspose.Words يجعل ملف التعريف هذا إلى صورة نقطية. |
| Vector | `1` | Aspose.Words تعرض ملف تعريف كرسومات متجهة. |
| Bitmap | `2` | Aspose.Words يستدعي GDI + لتقديم ملف تعريف إلى صورة نقطية ثم يحفظ الصورة النقطية في مستند الإخراج. |

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

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


