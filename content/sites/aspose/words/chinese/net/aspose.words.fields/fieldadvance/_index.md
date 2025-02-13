---
title: Class FieldAdvance
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Fields.FieldAdvance 班级. 实现 ADVANCE 字段
type: docs
weight: 1390
url: /zh/net/aspose.words.fields/fieldadvance/
---
## FieldAdvance class

实现 ADVANCE 字段。

```csharp
public class FieldAdvance : Field
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [FieldAdvance](fieldadvance/)() | 默认构造函数。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [DisplayResult](../../aspose.words.fields/field/displayresult/) { get; } | 获取表示显示字段结果的文本。 |
| [DownOffset](../../aspose.words.fields/fieldadvance/downoffset/) { get; set; } | 获取或设置字段后面的文本应向下移动的点数。 |
| [End](../../aspose.words.fields/field/end/) { get; } | 获取代表字段end的节点。 |
| [Format](../../aspose.words.fields/field/format/) { get; } | 得到一个[`FieldFormat`](../fieldformat/)提供对字段格式的类型化访问的对象。 |
| [HorizontalPosition](../../aspose.words.fields/fieldadvance/horizontalposition/) { get; set; } | 获取或设置字段后面的文本应从列、框架或文本框的左边缘水平移动的点数 。 |
| [IsDirty](../../aspose.words.fields/field/isdirty/) { get; set; } | 获取或设置字段的当前结果是否由于对文档的其他修改而不再正确（陈旧）。 |
| [IsLocked](../../aspose.words.fields/field/islocked/) { get; set; } | 获取或设置字段是否被锁定（不应重新计算其结果）。 |
| [LeftOffset](../../aspose.words.fields/fieldadvance/leftoffset/) { get; set; } | 获取或设置字段后面的文本应向左移动的点数。 |
| [LocaleId](../../aspose.words.fields/field/localeid/) { get; set; } | 获取或设置字段的LCID。 |
| [Result](../../aspose.words.fields/field/result/) { get; set; } | 获取或设置字段分隔符和字段结尾之间的文本。 |
| [RightOffset](../../aspose.words.fields/fieldadvance/rightoffset/) { get; set; } | 获取或设置字段后面的文本应向右移动的点数。 |
| [Separator](../../aspose.words.fields/field/separator/) { get; } | 获取表示字段分隔符的节点。可以为空。 |
| [Start](../../aspose.words.fields/field/start/) { get; } | 获取表示字段开始的节点。 |
| virtual [Type](../../aspose.words.fields/field/type/) { get; } | 获取 Microsoft Word 字段类型。 |
| [UpOffset](../../aspose.words.fields/fieldadvance/upoffset/) { get; set; } | 获取或设置字段后面的文本应该向上移动的点数。 |
| [VerticalPosition](../../aspose.words.fields/fieldadvance/verticalposition/) { get; set; } | 获取或设置字段后面的文本应从页面顶部边缘垂直移动的点数 。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)() | 返回字段开始和字段分隔符之间的文本（或字段结束，如果没有分隔符）。 包括子字段的字段代码和字段结果。 |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)(bool) | 返回字段开始和字段分隔符之间的文本（如果没有分隔符，则返回字段结束）。 |
| [Remove](../../aspose.words.fields/field/remove/)() | 从文档中删除字段。在字段之后返回一个节点。如果字段的结尾是其父节点的最后一个 child ，则返回其父段落。如果该字段已被删除，则返回 **无效的**. |
| [Unlink](../../aspose.words.fields/field/unlink/)() | 执行字段取消链接。 |
| [Update](../../aspose.words.fields/field/update/)() | 执行字段更新。如果该字段已被更新，则抛出。 |
| [Update](../../aspose.words.fields/field/update/)(bool) | 执行字段更新。如果该字段已被更新，则抛出。 |

### 评论

将在词法上跟随该字段的文本显示的起点向右或向左移动， 向上或向下，或移动到特定的水平或垂直位置。

### 例子

显示如何插入 ADVANCE 字段并编辑其属性。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("This text is in its normal place.");

// 下面是使用 ADVANCE 字段调整其后文本位置的两种方法。
// 继续应用 ADVANCE 字段的效果，直到段落结束，
// 或另一个 ADVANCE 字段更新偏移/坐标值。
// 1 - 指定方向偏移：
FieldAdvance field = (FieldAdvance)builder.InsertField(FieldType.FieldAdvance, true);
field.RightOffset = "5";
field.UpOffset = "5";

Assert.AreEqual(" ADVANCE  \\r 5 \\u 5", field.GetFieldCode());

builder.Write("This text will be moved up and to the right.");

field = (FieldAdvance)builder.InsertField(FieldType.FieldAdvance, true);
field.DownOffset = "5";
field.LeftOffset = "100";

Assert.AreEqual(" ADVANCE  \\d 5 \\l 100", field.GetFieldCode());

builder.Writeln("This text is moved down and to the left, overlapping the previous text.");

// 2 - 将文本移动到坐标指定的位置：
field = (FieldAdvance)builder.InsertField(FieldType.FieldAdvance, true);
field.HorizontalPosition = "-100";
field.VerticalPosition = "200";

Assert.AreEqual(" ADVANCE  \\x -100 \\y 200", field.GetFieldCode());

builder.Write("This text is in a custom position.");

doc.Save(ArtifactsDir + "Field.ADVANCE.docx");
```

### 也可以看看

* class [Field](../field/)
* 命名空间 [Aspose.Words.Fields](../../aspose.words.fields/)
* 部件 [Aspose.Words](../../)


