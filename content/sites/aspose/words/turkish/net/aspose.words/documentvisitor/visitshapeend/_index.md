---
title: DocumentVisitor.VisitShapeEnd
second_title: Aspose.Words for .NET API Referansı
description: DocumentVisitor yöntem. Şeklin numaralandırılması sona erdiğinde çağrılır.
type: docs
weight: 390
url: /tr/net/aspose.words/documentvisitor/visitshapeend/
---
## DocumentVisitor.VisitShapeEnd method

Şeklin numaralandırılması sona erdiğinde çağrılır.

```csharp
public virtual VisitorAction VisitShapeEnd(Shape shape)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| shape | Shape | Ziyaret edilen nesne. |

### Geri dönüş değeri

A[`VisitorAction`](../../visitoraction/) numaralandırmaya nasıl devam edileceğini belirten değer.

### Örnekler

Bir grup şeklin nasıl oluşturulacağını ve içeriğini bir belge ziyaretçisi kullanarak nasıl yazdırılacağını gösterir.

```csharp
public void GroupOfShapes()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // SingleCornerSnipped, TopCornersSnipped, DiagonalCornersSnipped gibi "NonPrimitive" şekiller oluşturmanız gerekiyorsa,
    // TopCornersOneRoundedOneSnipped, SingleCornerRounded, TopCornersRounded, DiagonalCornersRounded
    // lütfen DocumentBuilder.InsertShape yöntemlerini kullanın.
    Shape balloon = new Shape(doc, ShapeType.Balloon)
    {
        Width = 200, 
        Height = 200,
        Stroke = { Color = Color.Red }
    };

    Shape cube = new Shape(doc, ShapeType.Cube)
    {
        Width = 100, 
        Height = 100,
        Stroke = { Color = Color.Blue }
    };

    GroupShape group = new GroupShape(doc);
    group.AppendChild(balloon);
    group.AppendChild(cube);

    Assert.True(group.IsGroup);

    builder.InsertNode(group);

    ShapeGroupPrinter printer = new ShapeGroupPrinter();
    group.Accept(printer);

    Console.WriteLine(printer.GetText());
}

/// <summary>
/// Ziyaret edilen bir şekil grubunun içeriğini konsola yazdırır.
/// </summary>
public class ShapeGroupPrinter : DocumentVisitor
{
    public ShapeGroupPrinter()
    {
        mBuilder = new StringBuilder();
    }

    public string GetText()
    {
        return mBuilder.ToString();
    }

    public override VisitorAction VisitGroupShapeStart(GroupShape groupShape)
    {
        mBuilder.AppendLine("Shape group started:");
        return VisitorAction.Continue;
    }

    public override VisitorAction VisitGroupShapeEnd(GroupShape groupShape)
    {
        mBuilder.AppendLine("End of shape group");
        return VisitorAction.Continue;
    }

    public override VisitorAction VisitShapeStart(Shape shape)
    {
        mBuilder.AppendLine("\tShape - " + shape.ShapeType + ":");
        mBuilder.AppendLine("\t\tWidth: " + shape.Width);
        mBuilder.AppendLine("\t\tHeight: " + shape.Height);
        mBuilder.AppendLine("\t\tStroke color: " + shape.Stroke.Color);
        mBuilder.AppendLine("\t\tFill color: " + shape.Fill.ForeColor);
        return VisitorAction.Continue;
    }

    public override VisitorAction VisitShapeEnd(Shape shape)
    {
        mBuilder.AppendLine("\tEnd of shape");
        return VisitorAction.Continue;
    }

    private readonly StringBuilder mBuilder;
}
```

### Ayrıca bakınız

* enum [VisitorAction](../../visitoraction/)
* class [Shape](../../../aspose.words.drawing/shape/)
* class [DocumentVisitor](../)
* ad alanı [Aspose.Words](../../documentvisitor/)
* toplantı [Aspose.Words](../../../)


