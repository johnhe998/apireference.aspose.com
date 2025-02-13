---
title: Forms2OleControl.Type
second_title: Aspose.Words for .NET API 参考
description: Forms2OleControl 财产. 获取 Forms 2.0 控件的类型
type: docs
weight: 50
url: /zh/net/aspose.words.drawing.ole/forms2olecontrol/type/
---
## Forms2OleControl.Type property

获取 Forms 2.0 控件的类型。

```csharp
public Forms2OleControlType Type { get; }
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

* enum [Forms2OleControlType](../../forms2olecontroltype/)
* class [Forms2OleControl](../)
* 命名空间 [Aspose.Words.Drawing.Ole](../../forms2olecontrol/)
* 部件 [Aspose.Words](../../../)


