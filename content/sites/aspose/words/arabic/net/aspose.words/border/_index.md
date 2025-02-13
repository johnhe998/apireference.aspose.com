---
title: Class Border
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Border فصل. يمثل حدًا لكائن .
type: docs
weight: 70
url: /ar/net/aspose.words/border/
---
## Border class

يمثل حدًا لكائن .

```csharp
public class Border : InternableComplexAttr
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Color](../../aspose.words/border/color/) { get; set; } | الحصول على لون الحد أو تعيينه . |
| [DistanceFromText](../../aspose.words/border/distancefromtext/) { get; set; } | الحصول على مسافة الحد أو تعيينها من النص أو من حافة الصفحة بالنقاط. |
| [IsVisible](../../aspose.words/border/isvisible/) { get; } | إرجاع صحيح إذا لم يكن LineStyle ليس LineStyle. |
| [LineStyle](../../aspose.words/border/linestyle/) { get; set; } | الحصول على نمط الحدود أو تعيينه . |
| [LineWidth](../../aspose.words/border/linewidth/) { get; set; } | الحصول على أو تحديد عرض الحد بالنقاط . |
| [Shadow](../../aspose.words/border/shadow/) { get; set; } | الحصول على أو تعيين قيمة تشير إلى ما إذا كانت الحدود لها ظل . |

## طُرق

| اسم | وصف |
| --- | --- |
| [ClearFormatting](../../aspose.words/border/clearformatting/)() | يعيد تعيين خصائص الحدود إلى القيم الافتراضية. |
| [Equals](../../aspose.words/border/equals/#equals)(Border) | لتحديد ما إذا كانت الحدود المحددة تساوي قيمة الحد الحالي. |
| override [Equals](../../aspose.words/border/equals/#equals_1)(object) | لتحديد ما إذا كان الكائن المحدد يساوي قيمة الكائن الحالي. |
| override [GetHashCode](../../aspose.words/border/gethashcode/)() | يعمل كدالة تجزئة لهذا النوع. |

### ملاحظات

يمكن تطبيق الحدود على عناصر المستند المختلفة بما في ذلك الفقرة ، تشغيل النص داخل فقرة أو خلية جدول.

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

يوضح كيفية إدراج فقرة بحد علوي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Border topBorder = builder.ParagraphFormat.Borders[BorderType.Top];
topBorder.Color = Color.Red;
topBorder.LineWidth = 4.0d;
topBorder.LineStyle = LineStyle.DashSmallGap;

builder.Writeln("Text with a red top border.");

doc.Save(ArtifactsDir + "Border.ParagraphTopBorder.docx");
```

### أنظر أيضا

* class [InternableComplexAttr](../internablecomplexattr/)
* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


