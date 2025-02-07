---
title: Class Chart
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.Charts.Chart فصل. يوفر الوصول إلى خصائص شكل المخطط .
type: docs
weight: 600
url: /ar/net/aspose.words.drawing.charts/chart/
---
## Chart class

يوفر الوصول إلى خصائص شكل المخطط .

```csharp
public class Chart
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [AxisX](../../aspose.words.drawing.charts/chart/axisx/) { get; } | يوفر الوصول إلى خصائص المحور X للمخطط. |
| [AxisY](../../aspose.words.drawing.charts/chart/axisy/) { get; } | يوفر الوصول إلى خصائص المحور ص في المخطط . |
| [AxisZ](../../aspose.words.drawing.charts/chart/axisz/) { get; } | يوفر الوصول إلى خصائص المحور Z في المخطط. |
| [Legend](../../aspose.words.drawing.charts/chart/legend/) { get; } | يوفر الوصول إلى خصائص وسيلة إيضاح الرسم البياني. |
| [Series](../../aspose.words.drawing.charts/chart/series/) { get; } | يوفر الوصول إلى مجموعة المسلسلات . |
| [SourceFullName](../../aspose.words.drawing.charts/chart/sourcefullname/) { get; set; } | يحصل على مسار واسم ملف xls / xlsx الذي يرتبط به هذا المخطط. |
| [Title](../../aspose.words.drawing.charts/chart/title/) { get; } | يوفر الوصول إلى خصائص عنوان المخطط . |

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


