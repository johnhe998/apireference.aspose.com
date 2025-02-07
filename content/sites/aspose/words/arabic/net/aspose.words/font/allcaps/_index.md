---
title: Font.AllCaps
second_title: Aspose.Words لمراجع .NET API
description: Font ملكية. True إذا تم تنسيق الخط على هيئة أحرف كبيرة .
type: docs
weight: 10
url: /ar/net/aspose.words/font/allcaps/
---
## Font.AllCaps property

True إذا تم تنسيق الخط على هيئة أحرف كبيرة .

```csharp
public bool AllCaps { get; set; }
```

### أمثلة

يوضح كيفية تنسيق تشغيل لعرض محتوياته بالأحرف الكبيرة.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);

// هناك طريقتان للحصول على تشغيل لعرض نصه الصغير بأحرف كبيرة دون تغيير المحتويات.
// 1 - اضبط علامة AllCaps لعرض جميع الأحرف بأحرف كبيرة عادية:
Run run = new Run(doc, "all capitals");
run.Font.AllCaps = true;
para.AppendChild(run);

para = (Paragraph)para.ParentNode.AppendChild(new Paragraph(doc));

// 2 - اضبط علامة SmallCaps لعرض جميع الأحرف بأحرف كبيرة صغيرة:
// إذا كان الحرف صغيرًا ، فسيظهر في شكله الكبير
// ولكن سيكون لها نفس ارتفاع الحرف الصغير (ارتفاع الخط x).
// ستظهر الأحرف الكبيرة في الأصل بنفس الشكل.
run = new Run(doc, "Small Capitals");
run.Font.SmallCaps = true;
para.AppendChild(run);

doc.Save(ArtifactsDir + "Font.Caps.docx");
```

### أنظر أيضا

* class [Font](../)
* مساحة الاسم [Aspose.Words](../../font/)
* المجسم [Aspose.Words](../../../)


