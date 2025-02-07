---
title: OleControl.Name
second_title: Aspose.Words per .NET API Reference
description: OleControl proprietà. Ottiene il nome del controllo ActiveX.
type: docs
weight: 20
url: /it/net/aspose.words.drawing.ole/olecontrol/name/
---
## OleControl.Name property

Ottiene il nome del controllo ActiveX.

```csharp
public string Name { get; }
```

### Esempi

Mostra come verificare le proprietà di un controllo ActiveX.

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

### Guarda anche

* class [OleControl](../)
* spazio dei nomi [Aspose.Words.Drawing.Ole](../../olecontrol/)
* assemblea [Aspose.Words](../../../)


