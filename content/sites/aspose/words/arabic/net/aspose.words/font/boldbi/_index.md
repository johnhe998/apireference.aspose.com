---
title: Font.BoldBi
second_title: Aspose.Words لمراجع .NET API
description: Font ملكية. True إذا تم تنسيق النص من اليمين إلى اليسار بتنسيق غامق .
type: docs
weight: 50
url: /ar/net/aspose.words/font/boldbi/
---
## Font.BoldBi property

True إذا تم تنسيق النص من اليمين إلى اليسار بتنسيق غامق .

```csharp
public bool BoldBi { get; set; }
```

### أمثلة

يوضح كيفية تحديد مجموعات منفصلة من إعدادات الخطوط للنص من اليمين إلى اليسار ومن اليمين إلى اليسار.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// تحديد مجموعة من إعدادات الخط للنص من اليسار إلى اليمين.
builder.Font.Name = "Courier New";
builder.Font.Size = 16;
builder.Font.Italic = false;
builder.Font.Bold = false;
builder.Font.LocaleId = new CultureInfo("en-US", false).LCID;

// تحديد مجموعة أخرى من إعدادات الخط للنص من اليمين إلى اليسار.
builder.Font.NameBi = "Andalus";
builder.Font.SizeBi = 24;
builder.Font.ItalicBi = true;
builder.Font.BoldBi = true;
builder.Font.LocaleIdBi = new CultureInfo("ar-AR", false).LCID;

// يمكننا استخدام علم Bidi للإشارة إلى ما إذا كان النص على وشك إضافته
// مع منشئ المستندات من اليمين إلى اليسار. عندما نضيف نصًا مع ضبط هذه العلامة على "صحيح" ،
// سيتم تنسيقه باستخدام مجموعة إعدادات الخط من اليمين إلى اليسار.
builder.Font.Bidi = true;
builder.Write("مرحبًا");

// اضبط العلم على خطأ ، ثم أضف نصًا من اليسار إلى اليمين.
// سيقوم مُنشئ المستندات بتنسيق هذه باستخدام مجموعة إعدادات الخط من اليسار إلى اليمين.
builder.Font.Bidi = false;
builder.Write(" Hello world!");

doc.Save(ArtifactsDir + "Font.Bidi.docx");
```

### أنظر أيضا

* class [Font](../)
* مساحة الاسم [Aspose.Words](../../font/)
* المجسم [Aspose.Words](../../../)


