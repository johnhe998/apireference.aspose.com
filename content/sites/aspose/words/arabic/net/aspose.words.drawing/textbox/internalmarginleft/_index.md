---
title: TextBox.InternalMarginLeft
second_title: Aspose.Words لمراجع .NET API
description: TextBox ملكية. يحدد الهامش الأيسر الداخلي بالنقاط للشكل .
type: docs
weight: 30
url: /ar/net/aspose.words.drawing/textbox/internalmarginleft/
---
## TextBox.InternalMarginLeft property

يحدد الهامش الأيسر الداخلي بالنقاط للشكل .

```csharp
public double InternalMarginLeft { get; set; }
```

### ملاحظات

القيمة الافتراضية هي 1/10 بوصة.

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

### أنظر أيضا

* class [TextBox](../)
* مساحة الاسم [Aspose.Words.Drawing](../../textbox/)
* المجسم [Aspose.Words](../../../)


