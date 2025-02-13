---
title: OleControl.Name
second_title: Aspose.Words för .NET API Referens
description: OleControl fast egendom. Hämtar namnet på ActiveXkontrollen.
type: docs
weight: 20
url: /sv/net/aspose.words.drawing.ole/olecontrol/name/
---
## OleControl.Name property

Hämtar namnet på ActiveX-kontrollen.

```csharp
public string Name { get; }
```

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

* class [OleControl](../)
* namnutrymme [Aspose.Words.Drawing.Ole](../../olecontrol/)
* hopsättning [Aspose.Words](../../../)


