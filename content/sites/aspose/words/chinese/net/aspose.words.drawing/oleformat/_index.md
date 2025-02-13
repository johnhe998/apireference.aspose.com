---
title: Class OleFormat
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Drawing.OleFormat 班级. 提供对 OLE 对象或 ActiveX 控件数据的访问
type: docs
weight: 1020
url: /zh/net/aspose.words.drawing/oleformat/
---
## OleFormat class

提供对 OLE 对象或 ActiveX 控件数据的访问。

```csharp
public class OleFormat
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [AutoUpdate](../../aspose.words.drawing/oleformat/autoupdate/) { get; set; } | 指定指向 OLE 对象的链接是否在 Microsoft Word 中自动更新。 |
| [Clsid](../../aspose.words.drawing/oleformat/clsid/) { get; } | 获取 OLE 对象的 CLSID。 |
| [IconCaption](../../aspose.words.drawing/oleformat/iconcaption/) { get; } | 获取 OLE 对象的图标标题。 |
| [IsLink](../../aspose.words.drawing/oleformat/islink/) { get; } | 如果 OLE 对象已链接（当[`SourceFullName`](./sourcefullname/)已指定）. |
| [IsLocked](../../aspose.words.drawing/oleformat/islocked/) { get; set; } | 指定到 OLE 对象的链接是否被锁定以防更新。 |
| [OleControl](../../aspose.words.drawing/oleformat/olecontrol/) { get; } | 获取[`OleControl`](./olecontrol/)如果此 OLE 对象是 ActiveX 控件，则为对象。否则此属性为空。 |
| [OleIcon](../../aspose.words.drawing/oleformat/oleicon/) { get; } | 获取 OLE 对象的绘图方面。什么时候 **真的**，OLE 对象显示为图标。 什么时候 **错误的** OLE 对象显示为 content. |
| [OlePackage](../../aspose.words.drawing/oleformat/olepackage/) { get; } | 提供访问权限[`OlePackage`](../olepackage/)如果 OLE 对象是 OLE 包。 否则返回 null。 |
| [ProgId](../../aspose.words.drawing/oleformat/progid/) { get; set; } | 获取或设置 OLE 对象的 ProgID。 |
| [SourceFullName](../../aspose.words.drawing/oleformat/sourcefullname/) { get; set; } | 获取或设置链接的 OLE 对象的源文件的路径和名称。 |
| [SourceItem](../../aspose.words.drawing/oleformat/sourceitem/) { get; set; } | 获取或设置用于标识正在链接的源文件部分的字符串。 |
| [SuggestedExtension](../../aspose.words.drawing/oleformat/suggestedextension/) { get; } | 如果要将当前嵌入对象保存到文件中，则获取建议的文件扩展名。 |
| [SuggestedFileName](../../aspose.words.drawing/oleformat/suggestedfilename/) { get; } | 如果要将当前嵌入对象保存到文件中，则获取建议的文件名。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [GetOleEntry](../../aspose.words.drawing/oleformat/getoleentry/)(string) | 获取 OLE 对象数据条目。 |
| [GetRawData](../../aspose.words.drawing/oleformat/getrawdata/)() | 获取 OLE 对象原始数据。 |
| [Save](../../aspose.words.drawing/oleformat/save/#save)(Stream) | 将嵌入对象的数据保存到指定的流中。 |
| [Save](../../aspose.words.drawing/oleformat/save/#save_1)(string) | 将嵌入对象的数据保存到具有指定名称的文件中。 |

### 评论

使用[`OleFormat`](../shape/oleformat/)属性来访问 OLE 对象的数据。 您不创建`OleFormat`直接上课。

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

* 命名空间 [Aspose.Words.Drawing](../../aspose.words.drawing/)
* 部件 [Aspose.Words](../../)


