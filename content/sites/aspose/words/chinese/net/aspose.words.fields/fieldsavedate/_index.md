---
title: Class FieldSaveDate
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Fields.FieldSaveDate 班级. 实现 SAVEDATE 字段
type: docs
weight: 2200
url: /zh/net/aspose.words.fields/fieldsavedate/
---
## FieldSaveDate class

实现 SAVEDATE 字段。

```csharp
public class FieldSaveDate : Field
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [FieldSaveDate](fieldsavedate/)() | 默认构造函数。 |

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
| [UseLunarCalendar](../../aspose.words.fields/fieldsavedate/uselunarcalendar/) { get; set; } | 获取或设置是使用回历农历还是希伯来农历。 |
| [UseSakaEraCalendar](../../aspose.words.fields/fieldsavedate/usesakaeracalendar/) { get; set; } | 获取或设置是否使用Saka Era日历。 |
| [UseUmAlQuraCalendar](../../aspose.words.fields/fieldsavedate/useumalquracalendar/) { get; set; } | 获取或设置是否使用 Um-al-Qura 日历。 |

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

检索上次保存文档的日期和时间。默认使用公历。

### 例子

说明如何使用 SAVEDATE 字段来显示文档最近使用 Microsoft Word 执行的保存操作的日期/时间。

```csharp
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.Writeln(" Date this document was last saved:");

// 我们可以使用 SAVEDATE 字段在文档上显示上次保存操作的日期和时间。
// 这些字段所指的保存操作是在 Microsoft Word 等应用程序中手动保存，
// 不是文档的 Save 方法。
// 下面是三种不同的日历类型，根据这些类型，SAVEDATE 字段可以显示日期/时间。
// 1 - 伊斯兰农历：
builder.Write("According to the Lunar Calendar - ");
FieldSaveDate field = (FieldSaveDate)builder.InsertField(FieldType.FieldSaveDate, true);
field.UseLunarCalendar = true;

Assert.AreEqual(" SAVEDATE  \\h", field.GetFieldCode());

// 2 - Umm al-Qura 日历：
builder.Write("\nAccording to the Umm al-Qura calendar - ");
field = (FieldSaveDate)builder.InsertField(FieldType.FieldSaveDate, true);
field.UseUmAlQuraCalendar = true;

Assert.AreEqual(" SAVEDATE  \\u", field.GetFieldCode());

// 3 - 印度国历：
builder.Write("\nAccording to the Indian National calendar - ");
field = (FieldSaveDate)builder.InsertField(FieldType.FieldSaveDate, true);
field.UseSakaEraCalendar = true;

Assert.AreEqual(" SAVEDATE  \\s", field.GetFieldCode());

// SAVEDATE 字段从 LastSavedTime 内置属性中提取日期/时间值。
// 文档的 Save 方法不会更新这个值，但我们仍然可以手动更新它。
doc.BuiltInDocumentProperties.LastSavedTime = DateTime.Now;

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.SAVEDATE.docx");
```

### 也可以看看

* class [Field](../field/)
* 命名空间 [Aspose.Words.Fields](../../aspose.words.fields/)
* 部件 [Aspose.Words](../../)


