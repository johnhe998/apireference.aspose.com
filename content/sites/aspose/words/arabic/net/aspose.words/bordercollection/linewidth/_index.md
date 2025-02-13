---
title: BorderCollection.LineWidth
second_title: Aspose.Words لمراجع .NET API
description: BorderCollection ملكية. الحصول على أو تحديد عرض الحد بالنقاط .
type: docs
weight: 90
url: /ar/net/aspose.words/bordercollection/linewidth/
---
## BorderCollection.LineWidth property

الحصول على أو تحديد عرض الحد بالنقاط .

```csharp
public double LineWidth { get; set; }
```

### ملاحظات

ترجع عرض الحد الأول في المجموعة.

يضبط عرض كل الحدود في المجموعة باستثناء الحدود القطرية.

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

* class [BorderCollection](../)
* مساحة الاسم [Aspose.Words](../../bordercollection/)
* المجسم [Aspose.Words](../../../)


