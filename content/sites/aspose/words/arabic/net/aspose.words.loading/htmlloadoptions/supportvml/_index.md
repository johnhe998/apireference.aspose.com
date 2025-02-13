---
title: HtmlLoadOptions.SupportVml
second_title: Aspose.Words لمراجع .NET API
description: HtmlLoadOptions ملكية. الحصول على أو تعيين قيمة تشير إلى ما إذا كان سيتم دعم صور VML.
type: docs
weight: 60
url: /ar/net/aspose.words.loading/htmlloadoptions/supportvml/
---
## HtmlLoadOptions.SupportVml property

الحصول على أو تعيين قيمة تشير إلى ما إذا كان سيتم دعم صور VML.

```csharp
public bool SupportVml { get; set; }
```

### أمثلة

يوضح كيفية دعم التعليقات الشرطية أثناء تحميل مستند HTML.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions();

// إذا كانت القيمة صحيحة ، فإننا نأخذ كود VML في الاعتبار أثناء تحليل المستند الذي تم تحميله.
loadOptions.SupportVml = supportVml;

// يحتوي هذا المستند على صورة JPEG ضمن "<! - [if gte vml 1] >" العلامات
// وصورة PNG مختلفة داخل "<! [if! vml] >" العلامات.
// إذا قمنا بتعيين علامة "SupportVml" على "true" ، فستقوم Aspose.Words بتحميل JPEG.
// إذا قمنا بتعيين هذه العلامة على "خطأ" ، فإن Aspose.Words سوف يقوم بتحميل PNG فقط.
Document doc = new Document(MyDir + "VML conditional.htm", loadOptions);

if (supportVml)
    Assert.AreEqual(ImageType.Jpeg, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
else
    Assert.AreEqual(ImageType.Png, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
```

### أنظر أيضا

* class [HtmlLoadOptions](../)
* مساحة الاسم [Aspose.Words.Loading](../../htmlloadoptions/)
* المجسم [Aspose.Words](../../../)


