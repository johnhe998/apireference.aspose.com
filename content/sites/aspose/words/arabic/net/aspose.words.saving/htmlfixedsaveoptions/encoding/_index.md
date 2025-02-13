---
title: HtmlFixedSaveOptions.Encoding
second_title: Aspose.Words لمراجع .NET API
description: HtmlFixedSaveOptions ملكية. يحدد الترميز الذي سيتم استخدامه عند التصدير إلى HTML. القيمة الافتراضية هيترميز UTF8 جديد صحيح UTF8 مع BOM .
type: docs
weight: 30
url: /ar/net/aspose.words.saving/htmlfixedsaveoptions/encoding/
---
## HtmlFixedSaveOptions.Encoding property

يحدد الترميز الذي سيتم استخدامه عند التصدير إلى HTML. القيمة الافتراضية هي`ترميز UTF8 جديد (صحيح)` (UTF-8 مع BOM) .

```csharp
public Encoding Encoding { get; set; }
```

### أمثلة

يوضح كيفية تعيين الترميز المراد استخدامه أثناء تصدير مستند إلى HTML.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello World!");

// الترميز الافتراضي هو UTF-8. إذا أردنا تمثيل وثيقتنا باستخدام ترميز مختلف ،
// يمكننا استخدام كائن SaveOptions لتعيين ترميز معين.
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    Encoding = Encoding.GetEncoding("ASCII")
};

Assert.AreEqual("US-ASCII", htmlFixedSaveOptions.Encoding.EncodingName);

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.UseEncoding.html", htmlFixedSaveOptions);
```

### أنظر أيضا

* class [HtmlFixedSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* المجسم [Aspose.Words](../../../)


