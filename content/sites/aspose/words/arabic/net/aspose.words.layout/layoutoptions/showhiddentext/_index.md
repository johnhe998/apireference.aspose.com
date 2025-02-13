---
title: LayoutOptions.ShowHiddenText
second_title: Aspose.Words لمراجع .NET API
description: LayoutOptions ملكية. الحصول على أو تعيين إشارة إلى ما إذا كان النص المخفي في المستند سيتم تقديمه أم لا. الإعداد الافتراضي خطأ.
type: docs
weight: 70
url: /ar/net/aspose.words.layout/layoutoptions/showhiddentext/
---
## LayoutOptions.ShowHiddenText property

الحصول على أو تعيين إشارة إلى ما إذا كان النص المخفي في المستند سيتم تقديمه أم لا. الإعداد الافتراضي خطأ.

```csharp
public bool ShowHiddenText { get; set; }
```

### ملاحظات

تؤثر هذه الخاصية على كل المحتوى المخفي ، وليس النص فقط.

### أمثلة

يوضح كيفية إخفاء النص في مستند الإخراج المعروض.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// أدخل نصًا مخفيًا ، ثم حدد ما إذا كنا نرغب في حذفه من المستند المقدم.
builder.Writeln("This text is not hidden.");
builder.Font.Hidden = true;
builder.Writeln("This text is hidden.");

doc.LayoutOptions.ShowHiddenText = showHiddenText;

doc.Save(ArtifactsDir + "Document.LayoutOptionsHiddenText.pdf");
```

### أنظر أيضا

* class [LayoutOptions](../)
* مساحة الاسم [Aspose.Words.Layout](../../layoutoptions/)
* المجسم [Aspose.Words](../../../)


