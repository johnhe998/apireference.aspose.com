---
title: CellFormat.Width
second_title: Aspose.Words لمراجع .NET API
description: CellFormat ملكية. الحصول على عرض الخلية بالنقاط .
type: docs
weight: 130
url: /ar/net/aspose.words.tables/cellformat/width/
---
## CellFormat.Width property

الحصول على عرض الخلية بالنقاط .

```csharp
public double Width { get; set; }
```

### ملاحظات

يتم حساب العرض بواسطة Aspose.Words عند تحميل المستندات وحفظها. حاليًا ، لا يتم دعم كل مجموعة من خصائص الجدول والخلية والمستند . قد لا تكون القيمة التي تم إرجاعها دقيقة لبعض المستندات. عرض الخلية كما تم حسابه بواسطة MS Word عند فتح المستند في MS Word.

لا يوصى بتعيين هذه الخاصية . لا يوجد ضمان بأن الخلية سيكون لها بالفعل العرض المحدد . يمكن تعديل العرض لاستيعاب محتويات الخلية في تخطيط جدول الاحتواء التلقائي . قد يكون للخلايا الموجودة في صفوف أخرى عرض متعارض الإعدادات. يمكن تغيير حجم الجدول ليناسب الحاوية أو لتلبية إعدادات عرض الجدول . جرب استخدام[`PreferredWidth`](../preferredwidth/) لتعيين عرض الخلية. تعيين مجموعات هذه الخاصية[`PreferredWidth`](../preferredwidth/)ضمنيًا منذ الإصدار 15.8.

### أمثلة

يوضح كيفية تنسيق الخلايا باستخدام منشئ المستندات.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Row 1, cell 1.");

// أدخل خلية ثانية ، ثم قم بتكوين خيارات حشو نص الخلية.
// سيطبق المنشئ هذه الإعدادات في خليته الحالية ، وسيتم إنشاء أي خلايا جديدة بعد ذلك.
builder.InsertCell();

CellFormat cellFormat = builder.CellFormat;
cellFormat.Width = 250;
cellFormat.LeftPadding = 30;
cellFormat.RightPadding = 30;
cellFormat.TopPadding = 30;
cellFormat.BottomPadding = 30;

builder.Write("Row 1, cell 2.");
builder.EndRow();
builder.EndTable();

// لم تتأثر الخلية الأولى بإعادة تكوين الحشو ، ولا تزال تحتفظ بالقيم الافتراضية.
Assert.AreEqual(0.0d, table.FirstRow.Cells[0].CellFormat.Width);
Assert.AreEqual(5.4d, table.FirstRow.Cells[0].CellFormat.LeftPadding);
Assert.AreEqual(5.4d, table.FirstRow.Cells[0].CellFormat.RightPadding);
Assert.AreEqual(0.0d, table.FirstRow.Cells[0].CellFormat.TopPadding);
Assert.AreEqual(0.0d, table.FirstRow.Cells[0].CellFormat.BottomPadding);

Assert.AreEqual(250.0d, table.FirstRow.Cells[1].CellFormat.Width);
Assert.AreEqual(30.0d, table.FirstRow.Cells[1].CellFormat.LeftPadding);
Assert.AreEqual(30.0d, table.FirstRow.Cells[1].CellFormat.RightPadding);
Assert.AreEqual(30.0d, table.FirstRow.Cells[1].CellFormat.TopPadding);
Assert.AreEqual(30.0d, table.FirstRow.Cells[1].CellFormat.BottomPadding);

// ستظل الخلية الأولى تنمو في مستند الإخراج لتتناسب مع حجم الخلية المجاورة لها.
doc.Save(ArtifactsDir + "DocumentBuilder.SetCellFormatting.docx");
```

يوضح كيفية إنشاء جدول بحدود مخصصة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartTable();

// تعيين خيارات تنسيق الجدول لمنشئ المستندات
// سيطبقها على كل صف وخلية نضيفها معها.
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.CellFormat.ClearFormatting();
builder.CellFormat.Width = 150;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.CellFormat.Shading.BackgroundPatternColor = Color.GreenYellow;
builder.CellFormat.WrapText = false;
builder.CellFormat.FitText = true;

builder.RowFormat.ClearFormatting();
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.RowFormat.Height = 50;
builder.RowFormat.Borders.LineStyle = LineStyle.Engrave3D;
builder.RowFormat.Borders.Color = Color.Orange;

builder.InsertCell();
builder.Write("Row 1, Col 1");

builder.InsertCell();
builder.Write("Row 1, Col 2");
builder.EndRow();

// سيؤدي تغيير التنسيق إلى تطبيقه على الخلية الحالية ،
// وأي خلايا جديدة ننشئها باستخدام المنشئ بعد ذلك.
// لن يؤثر هذا على الخلايا التي أضفناها سابقًا.
builder.CellFormat.Shading.ClearFormatting();

builder.InsertCell();
builder.Write("Row 2, Col 1");

builder.InsertCell();
builder.Write("Row 2, Col 2");

builder.EndRow();

// زيادة ارتفاع الصف ليناسب النص الرأسي.
builder.InsertCell();
builder.RowFormat.Height = 150;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Write("Row 3, Col 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Write("Row 3, Col 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "DocumentBuilder.InsertTable.docx");
```

### أنظر أيضا

* class [CellFormat](../)
* مساحة الاسم [Aspose.Words.Tables](../../cellformat/)
* المجسم [Aspose.Words](../../../)


