---
title: LoadOptions.LoadFormat
second_title: Aspose.Words لمراجع .NET API
description: LoadOptions ملكية. يحدد تنسيق المستند الذي سيتم تحميله. الافتراضي هوAuto .
type: docs
weight: 90
url: /ar/net/aspose.words.loading/loadoptions/loadformat/
---
## LoadOptions.LoadFormat property

يحدد تنسيق المستند الذي سيتم تحميله. الافتراضي هوAuto .

```csharp
public LoadFormat LoadFormat { get; set; }
```

### ملاحظات

يوصى بتحديد ملفAutoالقيمة والسماح لـ Aspose.Words بالكشف عن تنسيق الملف تلقائيًا. إذا كنت تعرف تنسيق المستند الذي أنت على وشك تحميله ، فيمكنك تحديد format بشكل صريح وسيؤدي ذلك إلى تقليل وقت التحميل بشكل طفيف من خلال الحمل المرتبط بالكشف التلقائي عن التنسيق. على خطأ ، سيتم استدعاء الاكتشاف التلقائي وسيتم إجراء محاولة ثانية لتحميل الملف.

### أمثلة

يوضح كيفية تحديد عنوان URI أساسي عند فتح مستند html.

```csharp
// لنفترض أننا نريد تحميل مستند .html يحتوي على صورة مرتبطة بواسطة URI نسبي
// أثناء وجود الصورة في موقع مختلف. في هذه الحالة ، سنحتاج إلى حل URI النسبي إلى واحد مطلق.
 // يمكننا توفير URI أساسي باستخدام كائن HtmlLoadOptions.
HtmlLoadOptions loadOptions = new HtmlLoadOptions(LoadFormat.Html, "", ImageDir);

Assert.AreEqual(LoadFormat.Html, loadOptions.LoadFormat);

Document doc = new Document(MyDir + "Missing image.html", loadOptions);

// بينما كانت الصورة معطلة في الإدخال .html ، ساعدنا URI المخصص في إصلاح الرابط.
Shape imageShape = (Shape)doc.GetChildNodes(NodeType.Shape, true)[0];
Assert.True(imageShape.IsImage);

// سيعرض هذا المستند الناتج الصورة المفقودة.
doc.Save(ArtifactsDir + "HtmlLoadOptions.BaseUri.docx");
```

### أنظر أيضا

* enum [LoadFormat](../../../aspose.words/loadformat/)
* class [LoadOptions](../)
* مساحة الاسم [Aspose.Words.Loading](../../loadoptions/)
* المجسم [Aspose.Words](../../../)


