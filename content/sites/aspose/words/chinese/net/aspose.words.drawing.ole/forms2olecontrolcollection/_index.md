---
title: Class Forms2OleControlCollection
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Drawing.Ole.Forms2OleControlCollection 班级. 代表集合Forms2OleControl对象.
type: docs
weight: 990
url: /zh/net/aspose.words.drawing.ole/forms2olecontrolcollection/
---
## Forms2OleControlCollection class

代表集合[`Forms2OleControl`](../forms2olecontrol/)对象.

```csharp
public class Forms2OleControlCollection
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [Forms2OleControlCollection](forms2olecontrolcollection/)() | 默认构造函数。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Count](../../aspose.words.drawing.ole/forms2olecontrolcollection/count/) { get; } | 获取集合中对象的计数。 |
| [Item](../../aspose.words.drawing.ole/forms2olecontrolcollection/item/) { get; } | 获取[`Forms2OleControl`](../forms2olecontrol/)指定索引处的对象。 |

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

* 命名空间 [Aspose.Words.Drawing.Ole](../../aspose.words.drawing.ole/)
* 部件 [Aspose.Words](../../)


