---
title: Font.TintAndShade
second_title: Aspose.Words لمراجع .NET API
description: Font ملكية. الحصول على أو تعيين قيمة مزدوجة لتفتيح أو تغميق اللون.
type: docs
weight: 520
url: /ar/net/aspose.words/font/tintandshade/
---
## Font.TintAndShade property

الحصول على أو تعيين قيمة مزدوجة لتفتيح أو تغميق اللون.

```csharp
public double TintAndShade { get; set; }
```

### ملاحظات

تتراوح القيم المسموح بها من -1 (الأغمق) إلى 1 (الأفتح) لهذه الخاصية . الصفر (0) محايد. تؤدي محاولة تعيين هذه الخاصية إلى قيمة أقل من -1 أو أكثر من 1 إلى أArgumentOutOfRangeException.

يؤدي تعيين هذه الخاصية لكائن الخط بألوان غير سمة إلى ظهور ملفInvalidOperationException.

### أمثلة

يوضح كيفية إنشاء واستخدام نمط ذي موضوع.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln();

// إنشاء نمط بخصائص خط النسق.
Style style = doc.Styles.Add(StyleType.Paragraph, "ThemedStyle");
style.Font.ThemeFont = ThemeFont.Major;
style.Font.ThemeColor = ThemeColor.Accent5;
style.Font.TintAndShade = 0.3;

builder.ParagraphFormat.StyleName = "ThemedStyle";
builder.Writeln("Text with themed style");
```

### أنظر أيضا

* class [Font](../)
* مساحة الاسم [Aspose.Words](../../font/)
* المجسم [Aspose.Words](../../../)


