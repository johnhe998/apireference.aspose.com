---
title: LoadOptions.BaseUri
second_title: Aspose.Words لمراجع .NET API
description: LoadOptions ملكية. الحصول على أو تعيين السلسلة التي سيتم استخدامها لحل URIs النسبية الموجودة في المستند إلى URIs المطلقة عند الحاجة . يمكن أن تكون سلسلة فارغة أو فارغة. الافتراضي هو فارغ.
type: docs
weight: 20
url: /ar/net/aspose.words.loading/loadoptions/baseuri/
---
## LoadOptions.BaseUri property

الحصول على أو تعيين السلسلة التي سيتم استخدامها لحل URIs النسبية الموجودة في المستند إلى URIs المطلقة عند الحاجة . يمكن أن تكون سلسلة فارغة أو فارغة. الافتراضي هو فارغ.

```csharp
public string BaseUri { get; set; }
```

### ملاحظات

تُستخدم هذه الخاصية لتحليل URIs النسبية إلى مطلقة في الحالات التالية:

1. عند تحميل مستند HTML من دفق ويحتوي المستند على صور ذات معرّف URI نسبي ولا يحتوي على URI أساسي محدد في عنصر BASE HTML.
2. عند حفظ مستند إلى PDF وتنسيقات أخرى ، لاسترداد الصور المرتبطة باستخدام URIs بحيث يمكن حفظ الصور في مستند الإخراج.

### أمثلة

يوضح كيفية فتح مستند HTML بصور من دفق باستخدام URI أساسي.

```csharp
using (Stream stream = File.OpenRead(MyDir + "Document.html"))
{
    // قم بتمرير URI للمجلد الأساسي أثناء تحميله
    // بحيث يمكن العثور على أي صور ذات URIs ذات صلة في مستند HTML.
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.BaseUri = ImageDir;

    Document doc = new Document(stream, loadOptions);

    // تحقق من أن الشكل الأول للمستند يحتوي على صورة صالحة.
    Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

    Assert.IsTrue(shape.IsImage);
    Assert.IsNotNull(shape.ImageData.ImageBytes);
    Assert.AreEqual(32.0, ConvertUtil.PointToPixel(shape.Width), 0.01);
    Assert.AreEqual(32.0, ConvertUtil.PointToPixel(shape.Height), 0.01);
}
```

### أنظر أيضا

* class [LoadOptions](../)
* مساحة الاسم [Aspose.Words.Loading](../../loadoptions/)
* المجسم [Aspose.Words](../../../)


