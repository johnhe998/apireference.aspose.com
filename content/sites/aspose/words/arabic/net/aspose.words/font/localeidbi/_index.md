---
title: Font.LocaleIdBi
second_title: Aspose.Words لمراجع .NET API
description: Font ملكية. الحصول على أو تعيين معرف الإعدادات المحلية اللغة للأحرف المنسقة من اليمين إلى اليسار.
type: docs
weight: 210
url: /ar/net/aspose.words/font/localeidbi/
---
## Font.LocaleIdBi property

الحصول على أو تعيين معرف الإعدادات المحلية (اللغة) للأحرف المنسقة من اليمين إلى اليسار.

```csharp
public int LocaleIdBi { get; set; }
```

### ملاحظات

للحصول على قائمة معرفات الإعدادات المحلية ، راجع https://msdn.microsoft.com/en-us/library/cc233965.aspx

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


