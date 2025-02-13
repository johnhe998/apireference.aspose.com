---
title: TextBox.FitShapeToText
second_title: Aspose.Words لمراجع .NET API
description: TextBox ملكية. تحديد ما إذا كان Microsoft Word سيزيد الشكل ليلائم النص.
type: docs
weight: 10
url: /ar/net/aspose.words.drawing/textbox/fitshapetotext/
---
## TextBox.FitShapeToText property

تحديد ما إذا كان Microsoft Word سيزيد الشكل ليلائم النص.

```csharp
public bool FitShapeToText { get; set; }
```

### ملاحظات

النظام الأساسي **خاطئة**.

### أمثلة

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

* class [TextBox](../)
* مساحة الاسم [Aspose.Words.Drawing](../../textbox/)
* المجسم [Aspose.Words](../../../)


