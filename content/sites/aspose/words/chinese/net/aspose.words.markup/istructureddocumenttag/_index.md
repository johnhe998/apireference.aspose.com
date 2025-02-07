---
title: Interface IStructuredDocumentTag
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Markup.IStructuredDocumentTag 界面. 定义通用数据的接口StructuredDocumentTag和StructuredDocumentTagRangeStart.
type: docs
weight: 3730
url: /zh/net/aspose.words.markup/istructureddocumenttag/
---
## IStructuredDocumentTag interface

定义通用数据的接口[`StructuredDocumentTag`](../structureddocumenttag/)和[`StructuredDocumentTagRangeStart`](../structureddocumenttagrangestart/).

```csharp
public interface IStructuredDocumentTag
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Color](../../aspose.words.markup/istructureddocumenttag/color/) { get; set; } | 获取或设置结构化文档标签的颜色。 |
| [Id](../../aspose.words.markup/istructureddocumenttag/id/) { get; } | 为此指定一个唯一的只读持久数字 ID **SDT**. |
| [IsShowingPlaceholderText](../../aspose.words.markup/istructureddocumenttag/isshowingplaceholdertext/) { get; set; } | 指定此内容是否 **SDT**应被解释为包含占位符 text （与 SDT 中的常规文本内容相反）。 |
| [Level](../../aspose.words.markup/istructureddocumenttag/level/) { get; } | 获取这个级别 **SDT**出现在文档树中。 |
| [LockContentControl](../../aspose.words.markup/istructureddocumenttag/lockcontentcontrol/) { get; set; } | 当设置为 true 时，此属性将禁止用户删除此 **SDT**. |
| [LockContents](../../aspose.words.markup/istructureddocumenttag/lockcontents/) { get; set; } | 当设置为 true 时，此属性将禁止用户编辑此内容 **SDT**. |
| [Placeholder](../../aspose.words.markup/istructureddocumenttag/placeholder/) { get; } | 获取[`BuildingBlock`](../../aspose.words.buildingblocks/buildingblock/)包含当此 SDT 运行内容为空时应显示的占位符文本， 关联的映射 XML 元素为空，如通过[`XmlMapping`](./xmlmapping/)element 或[`IsShowingPlaceholderText`](./isshowingplaceholdertext/)元素为真。 |
| [PlaceholderName](../../aspose.words.markup/istructureddocumenttag/placeholdername/) { get; set; } | 获取或设置名称[`BuildingBlock`](../../aspose.words.buildingblocks/buildingblock/)包含占位符文本。 |
| [SdtType](../../aspose.words.markup/istructureddocumenttag/sdttype/) { get; } | 获取 this 的类型 **结构化文档标签**. |
| [Tag](../../aspose.words.markup/istructureddocumenttag/tag/) { get; set; } | 指定与当前 SDT 节点关联的标签。 不能为空。 |
| [Title](../../aspose.words.markup/istructureddocumenttag/title/) { get; set; } | 指定与此关联的友好名称 **SDT**. 不能为空。 |
| [WordOpenXML](../../aspose.words.markup/istructureddocumenttag/wordopenxml/) { get; } | 获取一个字符串，该字符串表示包含在FlatOpc格式. |
| [XmlMapping](../../aspose.words.markup/istructureddocumenttag/xmlmapping/) { get; } | 获取一个对象，该对象表示此结构化文档标记到当前文档的自定义 XML 部分中的 XML 数据 的映射。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [IsRanged](../../aspose.words.markup/istructureddocumenttag/isranged/)() | 如果此实例是范围结构化文档标记，则返回 true。 |
| [StructuredDocumentTagNode](../../aspose.words.markup/istructureddocumenttag/structureddocumenttagnode/)() | 返回实现此接口的 Node 对象。 |

### 也可以看看

* 命名空间 [Aspose.Words.Markup](../../aspose.words.markup/)
* 部件 [Aspose.Words](../../)


