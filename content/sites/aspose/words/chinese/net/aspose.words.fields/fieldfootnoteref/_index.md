---
title: Class FieldFootnoteRef
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Fields.FieldFootnoteRef 班级. 实现 FOOTNOTEREF 字段
type: docs
weight: 1750
url: /zh/net/aspose.words.fields/fieldfootnoteref/
---
## FieldFootnoteRef class

实现 FOOTNOTEREF 字段。

```csharp
public class FieldFootnoteRef : Field
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [FieldFootnoteRef](fieldfootnoteref/)() | 默认构造函数。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [DisplayResult](../../aspose.words.fields/field/displayresult/) { get; } | 获取表示显示字段结果的文本。 |
| [End](../../aspose.words.fields/field/end/) { get; } | 获取代表字段end的节点。 |
| [Format](../../aspose.words.fields/field/format/) { get; } | 得到一个[`FieldFormat`](../fieldformat/)提供对字段格式的类型化访问的对象。 |
| [IsDirty](../../aspose.words.fields/field/isdirty/) { get; set; } | 获取或设置字段的当前结果是否由于对文档的其他修改而不再正确（陈旧）。 |
| [IsLocked](../../aspose.words.fields/field/islocked/) { get; set; } | 获取或设置字段是否被锁定（不应重新计算其结果）。 |
| [LocaleId](../../aspose.words.fields/field/localeid/) { get; set; } | 获取或设置字段的LCID。 |
| [Result](../../aspose.words.fields/field/result/) { get; set; } | 获取或设置字段分隔符和字段结尾之间的文本。 |
| [Separator](../../aspose.words.fields/field/separator/) { get; } | 获取表示字段分隔符的节点。可以为空。 |
| [Start](../../aspose.words.fields/field/start/) { get; } | 获取表示字段开始的节点。 |
| virtual [Type](../../aspose.words.fields/field/type/) { get; } | 获取 Microsoft Word 字段类型。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)() | 返回字段开始和字段分隔符之间的文本（或字段结束，如果没有分隔符）。 包括子字段的字段代码和字段结果。 |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)(bool) | 返回字段开始和字段分隔符之间的文本（如果没有分隔符，则返回字段结束）。 |
| [Remove](../../aspose.words.fields/field/remove/)() | 从文档中删除字段。在字段之后返回一个节点。如果字段的结尾是其父节点的最后一个 child ，则返回其父段落。如果该字段已被删除，则返回 **无效的**. |
| [Unlink](../../aspose.words.fields/field/unlink/)() | 执行字段取消链接。 |
| [Update](../../aspose.words.fields/field/update/)() | 执行字段更新。如果该字段已被更新，则抛出。 |
| [Update](../../aspose.words.fields/field/update/)(bool) | 执行字段更新。如果该字段已被更新，则抛出。 |

### 例子

显示如何使用 FOOTNOTEREF 字段交叉引用脚注。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("CrossRefBookmark");
builder.Write("Hello world!");
builder.InsertFootnote(FootnoteType.Footnote, "Cross referenced footnote.");
builder.EndBookmark("CrossRefBookmark");
builder.InsertParagraph();

// 插入一个 FOOTNOTEREF 字段，它允许我们在重复使用相同的脚注标记时多次引用脚注。
builder.Write("CrossReference: ");
FieldFootnoteRef field = (FieldFootnoteRef) builder.InsertField(FieldType.FieldFootnoteRef, true);

// 引用我们使用 FOOTNOTEREF 字段创建的书签。该书签包含一个脚注标记
// 属于我们插入的脚注。该字段将显示该脚注标记。
builder.MoveTo(field.Separator);
builder.Write("CrossRefBookmark");

Assert.AreEqual(" FOOTNOTEREF CrossRefBookmark", field.GetFieldCode());

doc.UpdateFields();

// 此字段仅适用于旧版本的 Microsoft Word。
doc.Save(ArtifactsDir + "Field.FOOTNOTEREF.doc");
```

### 也可以看看

* class [Field](../field/)
* 命名空间 [Aspose.Words.Fields](../../aspose.words.fields/)
* 部件 [Aspose.Words](../../)


