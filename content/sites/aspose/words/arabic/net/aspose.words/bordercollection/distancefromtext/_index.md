---
title: BorderCollection.DistanceFromText
second_title: Aspose.Words لمراجع .NET API
description: BorderCollection ملكية. الحصول على مسافة الحد أو تحديدها من النص بالنقاط .
type: docs
weight: 40
url: /ar/net/aspose.words/bordercollection/distancefromtext/
---
## BorderCollection.DistanceFromText property

الحصول على مسافة الحد أو تحديدها من النص بالنقاط .

```csharp
public double DistanceFromText { get; set; }
```

### ملاحظات

الحصول على المسافة من النص للحد الأول.

يضبط المسافة من النص لكل الحدود في المجموعة باستثناء الحدود القطرية.

ليس له أي تأثير وسيتم إعادة تعيينه تلقائيًا إلى الصفر لحدود خلايا الجدول.

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


