---
title: Forms2OleControlCollection.Count
second_title: Aspose.Words for .NET API 参考
description: Forms2OleControlCollection 财产. 获取集合中对象的计数
type: docs
weight: 20
url: /zh/net/aspose.words.drawing.ole/forms2olecontrolcollection/count/
---
## Forms2OleControlCollection.Count property

获取集合中对象的计数。

```csharp
public int Count { get; }
```

### 例子

演示如何访问嵌入在文档中的 OLE 控件及其子控件。

```csharp
Document doc = new Document(MyDir + "OLE ActiveX controls.docm");

// 形状在文档正文中存储和显示 OLE 对象。
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

Assert.AreEqual("6e182020-f460-11ce-9bcd-00aa00608e01", shape.OleFormat.Clsid.ToString());

Forms2OleControl oleControl = (Forms2OleControl)shape.OleFormat.OleControl;

// 一些 OLE 控件可能包含子控件，例如本文档中的具有三个选项按钮的控件。
Forms2OleControlCollection oleControlCollection = oleControl.ChildNodes;

Assert.AreEqual(3, oleControlCollection.Count);

Assert.AreEqual("C#", oleControlCollection[0].Caption);
Assert.AreEqual("1", oleControlCollection[0].Value);

Assert.AreEqual("Visual Basic", oleControlCollection[1].Caption);
Assert.AreEqual("0", oleControlCollection[1].Value);

Assert.AreEqual("Delphi", oleControlCollection[2].Caption);
Assert.AreEqual("0", oleControlCollection[2].Value);
```

### 也可以看看

* class [Forms2OleControlCollection](../)
* 命名空间 [Aspose.Words.Drawing.Ole](../../forms2olecontrolcollection/)
* 部件 [Aspose.Words](../../../)


