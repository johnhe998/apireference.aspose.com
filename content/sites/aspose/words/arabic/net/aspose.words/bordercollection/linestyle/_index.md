---
title: BorderCollection.LineStyle
second_title: Aspose.Words لمراجع .NET API
description: BorderCollection ملكية. الحصول على نمط الحدود أو تعيينه .
type: docs
weight: 80
url: /ar/net/aspose.words/bordercollection/linestyle/
---
## BorderCollection.LineStyle property

الحصول على نمط الحدود أو تعيينه .

```csharp
public LineStyle LineStyle { get; set; }
```

### ملاحظات

إرجاع نمط الحد الأول في المجموعة.

يضبط نمط كل الحدود في المجموعة باستثناء الحدود القطرية.

### أمثلة

يوضح كيفية إنشاء حد صفحة أخضر مموج بظل.

```csharp
Document doc = new Document();
PageSetup pageSetup = doc.Sections[0].PageSetup;

pageSetup.Borders.LineStyle = LineStyle.DoubleWave;
pageSetup.Borders.LineWidth = 2;
pageSetup.Borders.Color = Color.Green;
pageSetup.Borders.DistanceFromText = 24;
pageSetup.Borders.Shadow = true;

doc.Save(ArtifactsDir + "PageSetup.PageBorders.docx");
```

### أنظر أيضا

* enum [LineStyle](../../linestyle/)
* class [BorderCollection](../)
* مساحة الاسم [Aspose.Words](../../bordercollection/)
* المجسم [Aspose.Words](../../../)


