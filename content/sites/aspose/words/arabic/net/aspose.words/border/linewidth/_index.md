---
title: Border.LineWidth
second_title: Aspose.Words لمراجع .NET API
description: Border ملكية. الحصول على أو تحديد عرض الحد بالنقاط .
type: docs
weight: 50
url: /ar/net/aspose.words/border/linewidth/
---
## Border.LineWidth property

الحصول على أو تحديد عرض الحد بالنقاط .

```csharp
public double LineWidth { get; set; }
```

### ملاحظات

إذا قمت بتعيين عرض الخط أكبر من الصفر عندما يكون نمط الخط بلا شيء ، فسيتم تغيير نمط الخط تلقائيًا إلى سطر واحد.

### أمثلة

يوضح كيفية إدراج سلسلة محاطة بحد في المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Border.Color = Color.Green;
builder.Font.Border.LineWidth = 2.5d;
builder.Font.Border.LineStyle = LineStyle.DashDotStroker;

builder.Write("Text surrounded by green border.");

doc.Save(ArtifactsDir + "Border.FontBorder.docx");
```

### أنظر أيضا

* class [Border](../)
* مساحة الاسم [Aspose.Words](../../border/)
* المجسم [Aspose.Words](../../../)


