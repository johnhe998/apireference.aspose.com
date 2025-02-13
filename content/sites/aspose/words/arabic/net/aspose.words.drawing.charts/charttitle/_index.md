---
title: Class ChartTitle
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.Charts.ChartTitle فصل. يوفر الوصول إلى خصائص عنوان المخطط .
type: docs
weight: 750
url: /ar/net/aspose.words.drawing.charts/charttitle/
---
## ChartTitle class

يوفر الوصول إلى خصائص عنوان المخطط .

```csharp
public class ChartTitle
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Overlay](../../aspose.words.drawing.charts/charttitle/overlay/) { get; set; } | يحدد ما إذا كان يُسمح لعناصر المخطط الأخرى بالتداخل مع العنوان. بشكل افتراضي ، يكون التراكب خاطئًا. |
| [Show](../../aspose.words.drawing.charts/charttitle/show/) { get; set; } | لتحديد ما إذا كان العنوان سيظهر لهذا المخطط. القيمة الافتراضية هي صحيحة . |
| [Text](../../aspose.words.drawing.charts/charttitle/text/) { get; set; } | الحصول على نص عنوان المخطط أو تعيينه. إذا تم تحديد قيمة فارغة أو فارغة ، فسيتم عرض العنوان الذي تم إنشاؤه تلقائيًا. |

### أمثلة

يوضح كيفية إدراج مخطط وتعيين عنوان.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل شكل مخطط باستخدام أداة إنشاء المستندات واحصل على مخططها.
Shape chartShape = builder.InsertChart(ChartType.Bar, 400, 300);
Chart chart = chartShape.Chart;

// استخدم خاصية "Title" لمنح المخطط عنوانًا يظهر في أعلى منتصف منطقة المخطط.
ChartTitle title = chart.Title;
title.Text = "My Chart";

 // اضبط خاصية "Show" على "true" لجعل العنوان مرئيًا.
title.Show = true;

// عيّن خاصية "التراكب" على "صواب" امنح عناصر المخطط الأخرى مساحة أكبر من خلال السماح لهم بتداخل العنوان
title.Overlay = true;

doc.Save(ArtifactsDir + "Charts.ChartTitle.docx");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* المجسم [Aspose.Words](../../)


