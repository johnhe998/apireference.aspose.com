---
title: OleFormat.AutoUpdate
second_title: Aspose.Words for .NET API 参考
description: OleFormat 财产. 指定指向 OLE 对象的链接是否在 Microsoft Word 中自动更新
type: docs
weight: 10
url: /zh/net/aspose.words.drawing/oleformat/autoupdate/
---
## OleFormat.AutoUpdate property

指定指向 OLE 对象的链接是否在 Microsoft Word 中自动更新。

```csharp
public bool AutoUpdate { get; set; }
```

### 评论

默认值为 **错误的**.

### 例子

演示如何将嵌入的 OLE 对象提取到文件中。

```csharp
Document doc = new Document(MyDir + "OLE spreadsheet.docm");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

// 第一个形状中的 OLE 对象是 Microsoft Excel 电子表格。
OleFormat oleFormat = shape.OleFormat;

Assert.AreEqual("Excel.Sheet.12", oleFormat.ProgId);

// 我们的对象既不是自动更新也不是锁定更新。
Assert.False(oleFormat.AutoUpdate);
Assert.AreEqual(false, oleFormat.IsLocked);

// 如果我们打算将 OLE 对象保存到本地文件系统中的文件中，
// 我们可以使用“SuggestedExtension”属性来确定应用到文件的文件扩展名。
Assert.AreEqual(".xlsx", oleFormat.SuggestedExtension);

// 下面是两种将 OLE 对象保存到本地文件系统中的文件的方法。
// 1 - 通过流保存它：
using (FileStream fs = new FileStream(ArtifactsDir + "OLE spreadsheet extracted via stream" + oleFormat.SuggestedExtension, FileMode.Create))
{
    oleFormat.Save(fs);
}

// 2 - 直接保存到一个文件名：
oleFormat.Save(ArtifactsDir + "OLE spreadsheet saved directly" + oleFormat.SuggestedExtension);
```

### 也可以看看

* class [OleFormat](../)
* 命名空间 [Aspose.Words.Drawing](../../oleformat/)
* 部件 [Aspose.Words](../../../)


