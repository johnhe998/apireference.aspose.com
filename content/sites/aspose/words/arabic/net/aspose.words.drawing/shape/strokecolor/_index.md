---
title: Shape.StrokeColor
second_title: Aspose.Words لمراجع .NET API
description: Shape ملكية. يحدد لون ضربة الفرشاة .
type: docs
weight: 190
url: /ar/net/aspose.words.drawing/shape/strokecolor/
---
## Shape.StrokeColor property

يحدد لون ضربة الفرشاة .

```csharp
public Color StrokeColor { get; set; }
```

### ملاحظات

هذا هو اختصار لملف[`Color`](../../stroke/color/) منشأه.

القيمة الافتراضية هي Black.

### أمثلة

يوضح كيفية تعبئة شكل بلون خالص.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// اكتب بعض النص ، ثم قم بتغطيته بشكل عائم.
builder.Font.Size = 32;
builder.Writeln("Hello world!");

Shape shape = builder.InsertShape(ShapeType.CloudCallout, RelativeHorizontalPosition.LeftMargin, 25,
    RelativeVerticalPosition.TopMargin, 25, 250, 150, WrapType.None);

// استخدم خاصية "StrokeColor" لتعيين لون المخطط التفصيلي للشكل.
shape.StrokeColor = Color.CadetBlue;

// استخدم خاصية "FillColor" لتعيين لون المنطقة الداخلية للشكل.
shape.FillColor = Color.LightBlue;

// تحدد خاصية "العتامة" مدى شفافية اللون على مقياس من 0-1 ،
// مع كون 1 معتمًا تمامًا ، والصفر غير مرئي.
// يكون ملء الشكل افتراضيًا معتمًا تمامًا ، لذلك لا يمكننا رؤية النص الموجود في أعلى هذا الشكل.
Assert.AreEqual(1.0d, shape.Fill.Opacity);

// اضبط عتامة لون تعبئة الشكل على قيمة أقل حتى نتمكن من رؤية النص تحتها.
shape.Fill.Opacity = 0.3;

doc.Save(ArtifactsDir + "Shape.Fill.docx");
```

يوضح كيفية التكرار على كل الأشكال في المستند.

```csharp
{
    Document doc = new Document(MyDir + "Revision shape.docx");
    ShapeAppearancePrinter visitor = new ShapeAppearancePrinter();
    doc.Accept(visitor);

    Console.WriteLine(visitor.GetText());
}

/// <summary>
/// يسجل المعلومات المتعلقة بالمظهر حول الأشكال التي تمت زيارتها.
/// </summary>
private class ShapeAppearancePrinter : DocumentVisitor
{
    public ShapeAppearancePrinter()
    {
        mShapesVisited = 0;
        mTextIndentLevel = 0;
        mStringBuilder = new StringBuilder();
    }

    /// <summary>
    /// تلحق سطرًا بـ StringBuilder بحرف جدولة واحد مضاف مسبقًا لكل مستوى مسافة بادئة.
    /// </summary>
    private void AppendLine(string text)
    {
        for (int i = 0; i < mTextIndentLevel; i++) mStringBuilder.Append('\t');

        mStringBuilder.AppendLine(text);
    }

    /// <summary>
    /// إرجاع كل النص الذي قام StringBuilder بتجميعه.
    /// </summary>
    public string GetText()
    {
        return $"Shapes visited: {mShapesVisited}\n{mStringBuilder}";
    }

    /// <summary>
    /// يتم الاتصال به عندما يزور هذا الزائر بداية عقدة الشكل.
    /// </summary>
    public override VisitorAction VisitShapeStart(Shape shape)
    {
        AppendLine($"Shape found: {shape.ShapeType}");

        mTextIndentLevel++;

        if (shape.HasChart)
            AppendLine($"Has chart: {shape.Chart.Title.Text}");

        AppendLine($"Extrusion enabled: {shape.ExtrusionEnabled}");
        AppendLine($"Shadow enabled: {shape.ShadowEnabled}");
        AppendLine($"StoryType: {shape.StoryType}");

        if (shape.Stroked)
        {
            Assert.AreEqual(shape.Stroke.Color, shape.StrokeColor);
            AppendLine($"Stroke colors: {shape.Stroke.Color}, {shape.Stroke.Color2}");
            AppendLine($"Stroke weight: {shape.StrokeWeight}");

        }

        if (shape.Filled)
            AppendLine($"Filled: {shape.FillColor}");

        if (shape.OleFormat != null)
            AppendLine($"Ole found of type: {shape.OleFormat.ProgId}");

        if (shape.SignatureLine != null)
            AppendLine($"Found signature line for: {shape.SignatureLine.Signer}, {shape.SignatureLine.SignerTitle}");

        return VisitorAction.Continue;
    }

    /// <summary>
    /// يتم الاتصال به عندما يزور هذا الزائر نهاية عقدة الشكل.
    /// </summary>
    public override VisitorAction VisitShapeEnd(Shape shape)
    {
        mTextIndentLevel--;
        mShapesVisited++;
        AppendLine($"End of {shape.ShapeType}");

        return VisitorAction.Continue;
    }

    /// <summary>
    /// يتم الاستدعاء عندما يزور هذا الزائر بداية عقدة GroupShape.
    /// </summary>
    public override VisitorAction VisitGroupShapeStart(GroupShape groupShape)
    {
        AppendLine($"Shape group found: {groupShape.ShapeType}");
        mTextIndentLevel++;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// يتم الاستدعاء عندما يزور هذا الزائر نهاية عقدة GroupShape.
    /// </summary>
    public override VisitorAction VisitGroupShapeEnd(GroupShape groupShape)
    {
        mTextIndentLevel--;
        AppendLine($"End of {groupShape.ShapeType}");

        return VisitorAction.Continue;
    }

    private int mShapesVisited;
    private int mTextIndentLevel;
    private readonly StringBuilder mStringBuilder;
}
```

### أنظر أيضا

* class [Shape](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shape/)
* المجسم [Aspose.Words](../../../)


