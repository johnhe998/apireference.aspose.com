---
title: OleControl.IsForms2OleControl
second_title: Aspose.Words for .NET API 参考
description: OleControl 财产. 如果控件是Forms2OleControl.
type: docs
weight: 10
url: /zh/net/aspose.words.drawing.ole/olecontrol/isforms2olecontrol/
---
## OleControl.IsForms2OleControl property

如果控件是[`Forms2OleControl`](../../forms2olecontrol/).

```csharp
public virtual bool IsForms2OleControl { get; }
```

### 例子

演示如何验证 ActiveX 控件的属性。

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

### 也可以看看

* class [OleControl](../)
* 命名空间 [Aspose.Words.Drawing.Ole](../../olecontrol/)
* 部件 [Aspose.Words](../../../)


