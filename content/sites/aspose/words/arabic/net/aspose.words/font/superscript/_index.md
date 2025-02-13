---
title: Font.Superscript
second_title: Aspose.Words لمراجع .NET API
description: Font ملكية. True إذا كان تنسيق الخط مرتفعًا.
type: docs
weight: 440
url: /ar/net/aspose.words/font/superscript/
---
## Font.Superscript property

True إذا كان تنسيق الخط مرتفعًا.

```csharp
public bool Superscript { get; set; }
```

### أمثلة

يوضح كيفية تنسيق النص لتعويض موضعه.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);

// ارفع سلسلة النص هذه بمقدار 5 نقاط فوق خط الأساس.
Run run = new Run(doc, "Raised text. ");
run.Font.Position = 5;
para.AppendChild(run);

// قم بتخفيض سلسلة النص هذه بمقدار 10 نقاط أسفل خط الأساس.
run = new Run(doc, "Lowered text. ");
run.Font.Position = -10;
para.AppendChild(run);

// أضف سلسلة من النص العادي.
run = new Run(doc, "Text in its default position. ");
para.AppendChild(run);

// أضف سلسلة من النص الذي يظهر على هيئة خط منخفض.
run = new Run(doc, "Subscript. ");
run.Font.Subscript = true;
para.AppendChild(run);

// أضف سلسلة نصية تظهر بخط مرتفع.
run = new Run(doc, "Superscript.");
run.Font.Superscript = true;
para.AppendChild(run);

doc.Save(ArtifactsDir + "Font.PositionSubscript.docx");
```

### أنظر أيضا

* class [Font](../)
* مساحة الاسم [Aspose.Words](../../font/)
* المجسم [Aspose.Words](../../../)


