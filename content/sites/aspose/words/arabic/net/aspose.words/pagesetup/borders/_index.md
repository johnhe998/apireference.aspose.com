---
title: PageSetup.Borders
second_title: Aspose.Words لمراجع .NET API
description: PageSetup ملكية. الحصول على مجموعة من حدود الصفحة .
type: docs
weight: 50
url: /ar/net/aspose.words/pagesetup/borders/
---
## PageSetup.Borders property

الحصول على مجموعة من حدود الصفحة .

```csharp
public BorderCollection Borders { get; }
```

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

* class [BorderCollection](../../bordercollection/)
* class [PageSetup](../)
* مساحة الاسم [Aspose.Words](../../pagesetup/)
* المجسم [Aspose.Words](../../../)


