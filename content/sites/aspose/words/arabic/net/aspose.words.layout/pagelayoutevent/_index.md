---
title: Enum PageLayoutEvent
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Layout.PageLayoutEvent تعداد. رمز حدث يظهر أثناء إنشاء نموذج تخطيط الصفحة وعرضه.
type: docs
weight: 3170
url: /ar/net/aspose.words.layout/pagelayoutevent/
---
## PageLayoutEvent enumeration

رمز حدث يظهر أثناء إنشاء نموذج تخطيط الصفحة وعرضه.

تم بناء نموذج تخطيط الصفحة في خطوتين. أولاً ، "خطوة التحويل" ، هذا عندما يسحب تخطيط الصفحة محتوى المستند وينشئ رسمًا بيانيًا للكائن. في صفحات.

اعتمادًا على العملية التي أدت إلى تشغيل الإنشاء ، قد يتم عرض نموذج تخطيط الصفحة بشكل أكبر أو لا يتم تحويله إلى تنسيق صفحة ثابتة. على سبيل المثال ، لا يتطلب حساب عدد الصفحات في المستند أو تحديث الحقول العرض ، بينما يتطلب التصدير إلى Pdf.

```csharp
public enum PageLayoutEvent
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| None | `0` | القيمة الافتراضية |
| WatchDog | `1` | يتوافق مع نقطة تفتيش في الكود والتي غالبًا ما تتم زيارتها وتكون مناسبة لإيقاف العملية. |
| BuildStarted | `2` | بدأ إنشاء تخطيط الصفحة. أطلق مرة واحدة. هذا هو الحدث الأول الذي يحدث عندما[`UpdatePageLayout`](../../aspose.words/document/updatepagelayout/) يسمى . |
| BuildFinished | `3` | انتهى إنشاء تخطيط الصفحة. أطلق مرة واحدة. هذا هو الحدث الأخير الذي يحدث عندما[`UpdatePageLayout`](../../aspose.words/document/updatepagelayout/) يسمى . |
| ConversionStarted | `4` | بدأ تحويل نموذج المستند إلى تخطيط الصفحة. تم التشغيل مرة واحدة . يحدث هذا عندما يبدأ نموذج التخطيط في سحب محتوى المستند. |
| ConversionFinished | `5` | تم الانتهاء من تحويل نموذج المستند إلى تخطيط الصفحة. تم التشغيل مرة واحدة . يحدث هذا عندما يتوقف نموذج التخطيط عن سحب محتوى المستند. |
| ReflowStarted | `6` | بدأ إعادة تدفق تخطيط الصفحة. تم التشغيل مرة واحدة . يحدث هذا عندما يبدأ نموذج التخطيط في إعادة تدفق محتوى المستند. |
| ReflowFinished | `7` | انتهى إعادة تدفق تخطيط الصفحة. تم التشغيل مرة واحدة . يحدث هذا عندما يتوقف نموذج التخطيط عن إعادة تدفق محتوى المستند. |
| PartReflowStarted | `8` | بدأ إعادة تدفق الصفحة. لاحظ أن الصفحة قد تتدفق عدة مرات وأن إعادة التدفق قد تبدأ قبل أن تنتهي. |
| PartReflowFinished | `9` | انتهى إعادة تدفق الصفحة. لاحظ أن الصفحة قد تتدفق عدة مرات وأن إعادة التدفق قد تتم إعادة تشغيلها قبل أن تنتهي. |
| PartRenderingStarted | `10` | بدأ عرض الصفحة. يتم تشغيل هذا مرة واحدة لكل صفحة. |
| PartRenderingFinished | `11` | انتهى عرض الصفحة. يتم تشغيل هذا مرة واحدة لكل صفحة. |

### أمثلة

يوضح كيفية تتبع تغييرات التخطيط مع استدعاء التخطيط.

```csharp
[Test]
public void PageLayoutCallback()
{
    Document doc = new Document();
    doc.BuiltInDocumentProperties.Title = "My Document";

    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.Writeln("Hello world!");

    doc.LayoutOptions.Callback = new RenderPageLayoutCallback();
    doc.UpdatePageLayout();

    doc.Save(ArtifactsDir + "Layout.PageLayoutCallback.pdf");
}

/// <summary>
/// يخطرنا عندما نحفظ المستند بتنسيق صفحة ثابت
/// ويعرض صفحة ننفذها لإعادة تدفق الصفحة إلى صورة في نظام الملفات المحلي.
/// </summary>
private class RenderPageLayoutCallback : IPageLayoutCallback
{
    public void Notify(PageLayoutCallbackArgs a)
    {
        switch (a.Event)
        {
            case PageLayoutEvent.PartReflowFinished:
                NotifyPartFinished(a);
                break;
            case PageLayoutEvent.ConversionFinished:
                NotifyConversionFinished(a);
                break;
        }
    }

    private void NotifyPartFinished(PageLayoutCallbackArgs a)
    {
        Console.WriteLine($"Part at page {a.PageIndex + 1} reflow.");
        RenderPage(a, a.PageIndex);
    }

    private void NotifyConversionFinished(PageLayoutCallbackArgs a)
    {
        Console.WriteLine($"Document \"{a.Document.BuiltInDocumentProperties.Title}\" converted to page format.");
    }

    private void RenderPage(PageLayoutCallbackArgs a, int pageIndex)
    {
        ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png) { PageSet = new PageSet(pageIndex) };

        using (FileStream stream =
            new FileStream(ArtifactsDir + $@"PageLayoutCallback.page-{pageIndex + 1} {++mNum}.png",
                FileMode.Create))
            a.Document.Save(stream, saveOptions);
    }

    private int mNum;
}
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Layout](../../aspose.words.layout/)
* المجسم [Aspose.Words](../../)


