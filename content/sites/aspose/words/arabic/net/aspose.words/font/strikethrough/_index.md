---
title: Font.StrikeThrough
second_title: Aspose.Words لمراجع .NET API
description: Font ملكية. True إذا تم تنسيق الخط كنص يتوسطه خط .
type: docs
weight: 390
url: /ar/net/aspose.words/font/strikethrough/
---
## Font.StrikeThrough property

True إذا تم تنسيق الخط كنص يتوسطه خط .

```csharp
public bool StrikeThrough { get; set; }
```

### أمثلة

يوضح كيفية إضافة خط يتوسطه خط إلى النص.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);

Run run = new Run(doc, "Text with a single-line strikethrough.");
run.Font.StrikeThrough = true;
para.AppendChild(run);

para = (Paragraph)para.ParentNode.AppendChild(new Paragraph(doc));

run = new Run(doc, "Text with a double-line strikethrough.");
run.Font.DoubleStrikeThrough = true;
para.AppendChild(run);

doc.Save(ArtifactsDir + "Font.StrikeThrough.docx");
```

### أنظر أيضا

* class [Font](../)
* مساحة الاسم [Aspose.Words](../../font/)
* المجسم [Aspose.Words](../../../)


