---
title: Forms2OleControl.ChildNodes
second_title: Aspose.Words för .NET API Referens
description: Forms2OleControl fast egendom. Får en samling av omedelbara barnkontroller.
type: docs
weight: 20
url: /sv/net/aspose.words.drawing.ole/forms2olecontrol/childnodes/
---
## Forms2OleControl.ChildNodes property

Får en samling av omedelbara barnkontroller.

```csharp
public Forms2OleControlCollection ChildNodes { get; }
```

### Anmärkningar

Returnerar **null** om denna kontroll inte kan få barn.

### Exempel

Visar hur du verifierar egenskaperna för en ActiveX-kontroll.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");

Shape shape = (Shape) doc.GetChild(NodeType.Shape, 0, true);
OleControl oleControl = shape.OleFormat.OleControl;

Assert.AreEqual(null, oleControl.Name);

if (oleControl.IsForms2OleControl)
{
    Forms2OleControl checkBox = (Forms2OleControl) oleControl;
    Assert.AreEqual("Первый", checkBox.Caption);
    Assert.AreEqual("0", checkBox.Value);
    Assert.AreEqual(true, checkBox.Enabled);
    Assert.AreEqual(Forms2OleControlType.CheckBox, checkBox.Type);
    Assert.AreEqual(null, checkBox.ChildNodes);
}
```

### Se även

* class [Forms2OleControlCollection](../../forms2olecontrolcollection/)
* class [Forms2OleControl](../)
* namnutrymme [Aspose.Words.Drawing.Ole](../../forms2olecontrol/)
* hopsättning [Aspose.Words](../../../)


