---
title: Class Range
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Range 班级. 表示文档中的一个连续区域
type: docs
weight: 4270
url: /zh/net/aspose.words/range/
---
## Range class

表示文档中的一个连续区域。

```csharp
public class Range
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Bookmarks](../../aspose.words/range/bookmarks/) { get; } | 返回一个[`Bookmarks`](./bookmarks/)代表范围内所有书签的集合。 |
| [Fields](../../aspose.words/range/fields/) { get; } | 返回一个[`Fields`](./fields/)代表范围内所有字段的集合。 |
| [FormFields](../../aspose.words/range/formfields/) { get; } | 返回一个[`FormFields`](./formfields/)代表范围内所有表单字段的集合。 |
| [StructuredDocumentTags](../../aspose.words/range/structureddocumenttags/) { get; } | 返回一个[`StructuredDocumentTags`](./structureddocumenttags/)表示范围内所有结构化文档标签的集合。 |
| [Text](../../aspose.words/range/text/) { get; } | 获取范围的文本。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [Delete](../../aspose.words/range/delete/)() | 删除范围内的所有字符。 |
| [NormalizeFieldTypes](../../aspose.words/range/normalizefieldtypes/)() | 更改字段类型值[`FieldType`](../../aspose.words.fields/fieldchar/fieldtype/)的[`FieldStart`](../../aspose.words.fields/fieldstart/),[`FieldSeparator`](../../aspose.words.fields/fieldseparator/),[`FieldEnd`](../../aspose.words.fields/fieldend/) 在此范围内，以便它们对应于字段代码中包含的字段类型。 |
| [Replace](../../aspose.words/range/replace/#replace_2)(Regex, string) | 用另一个字符串替换所有出现的由正则表达式指定的字符模式。 |
| [Replace](../../aspose.words/range/replace/#replace)(string, string) | 用替换字符串替换所有出现的指定字符串模式。 |
| [Replace](../../aspose.words/range/replace/#replace_3)(Regex, string, FindReplaceOptions) | 用另一个字符串替换所有出现的由正则表达式指定的字符模式。 |
| [Replace](../../aspose.words/range/replace/#replace_1)(string, string, FindReplaceOptions) | 用替换字符串替换所有出现的指定字符串模式。 |
| [ToDocument](../../aspose.words/range/todocument/)() | 构造一个包含范围的新完整文档。 |
| [UnlinkFields](../../aspose.words/range/unlinkfields/)() | 取消链接此范围内的字段。 |
| [UpdateFields](../../aspose.words/range/updatefields/)() | 更新此范围内文档字段的值。 |

### 评论

文档由节点树表示，节点提供 operations 以使用树，但如果将 document 视为连续的文本序列，则某些操作更容易执行。

**范围**是一个“外观”接口，它提供将 document 或文档部分视为“平面”文本的方法，而不管 document 节点是否存储在树状对象模型中。

**范围**不包含任何文本或节点，它只是文档片段上的视图或“窗口” 。

### 例子

显示如何获取范围涵盖的所有节点的文本内容。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Hello world!");

Assert.AreEqual("Hello world!", doc.Range.Text.Trim());
```

### 也可以看看

* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


