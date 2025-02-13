---
title: Enum PageBorderDistanceFrom
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.PageBorderDistanceFrom تعداد. يحدد موضع حد الصفحة بالنسبة لهامش الصفحة.
type: docs
weight: 4110
url: /ar/net/aspose.words/pageborderdistancefrom/
---
## PageBorderDistanceFrom enumeration

يحدد موضع حد الصفحة بالنسبة لهامش الصفحة.

```csharp
public enum PageBorderDistanceFrom
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Text | `0` | يتم قياس موضع الحد من هامش الصفحة. |
| PageEdge | `1` | يتم قياس موضع الحد من حافة الصفحة. |

### أمثلة

يوضح كيفية إنشاء حد شريط أزرق عريض أعلى الصفحة الأولى.

```csharp
Document doc = new Document();

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.BorderAlwaysInFront = false;
pageSetup.BorderDistanceFrom = PageBorderDistanceFrom.PageEdge;
pageSetup.BorderAppliesTo = PageBorderAppliesTo.FirstPage;

Border border = pageSetup.Borders[BorderType.Top];
border.LineStyle = LineStyle.Single;
border.LineWidth = 30;
border.Color = Color.Blue;
border.DistanceFromText = 0;

doc.Save(ArtifactsDir + "PageSetup.PageBorderProperties.docx");
```

### أنظر أيضا

* class [PageSetup](../pagesetup/)
* property [BorderDistanceFrom](../pagesetup/borderdistancefrom/)
* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


