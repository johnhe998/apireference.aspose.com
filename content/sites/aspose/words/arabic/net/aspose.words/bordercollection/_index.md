---
title: Class BorderCollection
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.BorderCollection فصل. مجموعة من الكائنات الحدودية .
type: docs
weight: 80
url: /ar/net/aspose.words/bordercollection/
---
## BorderCollection class

مجموعة من الكائنات الحدودية .

```csharp
public sealed class BorderCollection : IEnumerable<Border>
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Bottom](../../aspose.words/bordercollection/bottom/) { get; } | يحصل على الحد السفلي . |
| [Color](../../aspose.words/bordercollection/color/) { get; set; } | الحصول على لون الحد أو تعيينه . |
| [Count](../../aspose.words/bordercollection/count/) { get; } | الحصول على رقم الحدود في المجموعة. |
| [DistanceFromText](../../aspose.words/bordercollection/distancefromtext/) { get; set; } | الحصول على مسافة الحد أو تحديدها من النص بالنقاط . |
| [Horizontal](../../aspose.words/bordercollection/horizontal/) { get; } | الحصول على الحد الأفقي المستخدم بين الخلايا أو مطابقة الفقرات. |
| [Item](../../aspose.words/bordercollection/item/) { get; } | استرداد كائن حد حسب نوع الحد. (2 indexers) |
| [Left](../../aspose.words/bordercollection/left/) { get; } | يحصل على الحد الأيسر . |
| [LineStyle](../../aspose.words/bordercollection/linestyle/) { get; set; } | الحصول على نمط الحدود أو تعيينه . |
| [LineWidth](../../aspose.words/bordercollection/linewidth/) { get; set; } | الحصول على أو تحديد عرض الحد بالنقاط . |
| [Right](../../aspose.words/bordercollection/right/) { get; } | يحصل على الحد الصحيح . |
| [Shadow](../../aspose.words/bordercollection/shadow/) { get; set; } | الحصول على أو تعيين قيمة تشير إلى ما إذا كانت الحدود لها ظل . |
| [Top](../../aspose.words/bordercollection/top/) { get; } | الحصول على الحد العلوي . |
| [Vertical](../../aspose.words/bordercollection/vertical/) { get; } | الحصول على الحد الرأسي المستخدم بين الخلايا . |

## طُرق

| اسم | وصف |
| --- | --- |
| [ClearFormatting](../../aspose.words/bordercollection/clearformatting/)() | يزيل كافة حدود الكائن . |
| [Equals](../../aspose.words/bordercollection/equals/#equals)(BorderCollection) | مقارنة مجموعات الحدود . |
| [GetEnumerator](../../aspose.words/bordercollection/getenumerator/)() | إرجاع كائن العداد الذي يمكن استخدامه للتكرار عبر كافة الحدود في المجموعة. |

### ملاحظات

عناصر المستند المختلفة لها حدود مختلفة . على سبيل المثال ، يحتوي تنسيق الفقرة على حدود سفلية ، ويسرى ، ويمين ، وأعلى.

### أمثلة

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

* class [Border](../border/)
* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


