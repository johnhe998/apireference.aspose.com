---
title: GroupShape.Accept
second_title: Aspose.Words für .NET-API-Referenz
description: GroupShape methode. Akzeptiert einen Besucher.
type: docs
weight: 30
url: /de/net/aspose.words.drawing/groupshape/accept/
---
## GroupShape.Accept method

Akzeptiert einen Besucher.

```csharp
public override bool Accept(DocumentVisitor visitor)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| visitor | DocumentVisitor | Der Besucher, der die Knoten besucht. |

### Rückgabewert

True, wenn alle Knoten besucht wurden; false, wenn DocumentVisitor den Vorgang beendet hat, bevor alle Knoten besucht wurden.

### Bemerkungen

Listet diesen Knoten und alle seine untergeordneten Elemente auf. Jeder Knoten ruft eine entsprechende Methode auf DocumentVisitor auf.

Weitere Informationen finden Sie im Besucher-Entwurfsmuster.

Anrufe[`VisitGroupShapeStart`](../../../aspose.words/documentvisitor/visitgroupshapestart/) , ruft dann an[`Accept`](../../../aspose.words/node/accept/) für alle untergeordneten Shapes dieser Gruppenform und Aufrufe[`VisitGroupShapeEnd`](../../../aspose.words/documentvisitor/visitgroupshapeend/) am Ende.

### Beispiele

Zeigt, wie Sie eine Gruppe von Formen erstellen und ihren Inhalt mit einem Dokumentbesucher drucken.

```csharp
public void GroupOfShapes()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Wenn Sie "NonPrimitive"-Formen erstellen müssen, z. B. SingleCornerSnipped, TopCornersSnipped, DiagonalCornersSnipped,
    // TopCornersOneRoundedOneSnipped, SingleCornerRounded, TopCornersRounded, DiagonalCornersRounded
    // Bitte verwenden Sie DocumentBuilder.InsertShape-Methoden.
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
/// Gibt den Inhalt einer besuchten Shape-Gruppe an die Konsole aus.
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

### Siehe auch

* class [DocumentVisitor](../../../aspose.words/documentvisitor/)
* class [GroupShape](../)
* namensraum [Aspose.Words.Drawing](../../groupshape/)
* Montage [Aspose.Words](../../../)


