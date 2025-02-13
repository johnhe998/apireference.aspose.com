---
title: Font.Scaling
second_title: Aspose.Words لمراجع .NET API
description: Font ملكية. الحصول على أو تعيين قياس عرض الأحرف بالنسبة المئوية.
type: docs
weight: 310
url: /ar/net/aspose.words/font/scaling/
---
## Font.Scaling property

الحصول على أو تعيين قياس عرض الأحرف بالنسبة المئوية.

```csharp
public int Scaling { get; set; }
```

### أمثلة

يوضح كيفية تعيين القياس الأفقي والتباعد بين الأحرف.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أضف سلسلة نصية وقم بزيادة عرض الحرف إلى 150٪.
builder.Font.Scaling = 150;
builder.Writeln("Wide characters");

// أضف سلسلة نصية وأضف 1 نقطة من التباعد الأفقي الإضافي بين كل حرف.
builder.Font.Spacing = 1;
builder.Writeln("Expanded by 1pt");

// أضف سلسلة نصية وقرب الأحرف معًا بمقدار 1 نقطة.
builder.Font.Spacing = -1;
builder.Writeln("Condensed by 1pt");

doc.Save(ArtifactsDir + "Font.ScalingSpacing.docx");
```

### أنظر أيضا

* class [Font](../)
* مساحة الاسم [Aspose.Words](../../font/)
* المجسم [Aspose.Words](../../../)


