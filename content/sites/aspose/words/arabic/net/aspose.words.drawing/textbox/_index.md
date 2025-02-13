---
title: Class TextBox
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.TextBox فصل. يحدد السمات التي تحدد كيفية عرض النص داخل الشكل.
type: docs
weight: 1170
url: /ar/net/aspose.words.drawing/textbox/
---
## TextBox class

يحدد السمات التي تحدد كيفية عرض النص داخل الشكل.

```csharp
public class TextBox
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [FitShapeToText](../../aspose.words.drawing/textbox/fitshapetotext/) { get; set; } | تحديد ما إذا كان Microsoft Word سيزيد الشكل ليلائم النص. |
| [InternalMarginBottom](../../aspose.words.drawing/textbox/internalmarginbottom/) { get; set; } | يحدد الهامش السفلي الداخلي بالنقاط للشكل . |
| [InternalMarginLeft](../../aspose.words.drawing/textbox/internalmarginleft/) { get; set; } | يحدد الهامش الأيسر الداخلي بالنقاط للشكل . |
| [InternalMarginRight](../../aspose.words.drawing/textbox/internalmarginright/) { get; set; } | يحدد الهامش الأيمن الداخلي بالنقاط للشكل . |
| [InternalMarginTop](../../aspose.words.drawing/textbox/internalmargintop/) { get; set; } | يحدد الهامش العلوي الداخلي بالنقاط للشكل . |
| [LayoutFlow](../../aspose.words.drawing/textbox/layoutflow/) { get; set; } | يحدد تدفق تخطيط النص في شكل. |
| [Next](../../aspose.words.drawing/textbox/next/) { get; set; } | إرجاع أو تعيين مربع نص يمثل مربع النص التالي في تسلسل من الأشكال. |
| [Parent](../../aspose.words.drawing/textbox/parent/) { get; } | الحصول على شكل أصل لمربع النص. |
| [Previous](../../aspose.words.drawing/textbox/previous/) { get; } | إرجاع مربع نص يمثل مربع نص سابق في تسلسل من الأشكال. |
| [TextBoxWrapMode](../../aspose.words.drawing/textbox/textboxwrapmode/) { get; set; } | يحدد كيفية التفاف النص داخل الشكل. |
| [VerticalAnchor](../../aspose.words.drawing/textbox/verticalanchor/) { get; set; } | يحدد المحاذاة الرأسية للنص داخل الشكل. |

## طُرق

| اسم | وصف |
| --- | --- |
| [BreakForwardLink](../../aspose.words.drawing/textbox/breakforwardlink/)() | يكسر الارتباط إلى مربع النص التالي. |
| [IsValidLinkTarget](../../aspose.words.drawing/textbox/isvalidlinktarget/)(TextBox) | يحدد ما إذا كان يمكن ربط مربع النص هذا بصندوق النص الهدف. |

### ملاحظات

استخدم ال[`TextBox`](../shape/textbox/) للوصول إلى خصائص النص الخاصة بالشكل . لا يمكنك إنشاء مثيلات لملف`TextBox` فئة مباشرة.

### أمثلة

يوضح كيفية تعيين الهوامش الداخلية لمربع نص.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل مربع نص آخر بهوامش محددة.
Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 100, 100);
TextBox textBox = textBoxShape.TextBox;
textBox.InternalMarginTop = 15;
textBox.InternalMarginBottom = 15;
textBox.InternalMarginLeft = 15;
textBox.InternalMarginRight = 15;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Write("Text placed according to textbox margins.");

doc.Save(ArtifactsDir + "Shape.TextBoxMargins.docx");
```

يوضح كيفية تعيين اتجاه النص داخل مربع نص.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// انقل منشئ المستندات إلى داخل TextBox وأضف نصًا.
builder.MoveTo(textBoxShape.LastParagraph);
builder.Writeln("Hello world!");
builder.Write("Hello again!");

// قم بتعيين خاصية "LayoutFlow" لتعيين اتجاه لمحتويات النص في مربع النص هذا.
textBox.LayoutFlow = layoutFlow;

doc.Save(ArtifactsDir + "Shape.TextBoxLayoutFlow.docx");
```

يوضح كيفية جعل مربع نص يغير حجمه ليلائم محتوياته بإحكام.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// قم بتطبيق هذه القيم على كل من هذين العضوين للحصول على الشكل الأصل المناسب
// بإحكام حول محتويات النص ، متجاهلاً الأبعاد التي حددناها.
textBox.FitShapeToText = true;
textBox.TextBoxWrapMode = TextBoxWrapMode.None;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Write("Text fit tightly inside textbox.");

doc.Save(ArtifactsDir + "Shape.TextBoxFitShapeToText.docx");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Drawing](../../aspose.words.drawing/)
* المجسم [Aspose.Words](../../)


