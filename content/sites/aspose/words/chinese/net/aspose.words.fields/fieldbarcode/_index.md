---
title: Class FieldBarcode
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Fields.FieldBarcode 班级. 实现 BARCODE 字段
type: docs
weight: 1480
url: /zh/net/aspose.words.fields/fieldbarcode/
---
## FieldBarcode class

实现 BARCODE 字段。

```csharp
public class FieldBarcode : Field
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [FieldBarcode](fieldbarcode/)() | 默认构造函数。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [DisplayResult](../../aspose.words.fields/field/displayresult/) { get; } | 获取表示显示字段结果的文本。 |
| [End](../../aspose.words.fields/field/end/) { get; } | 获取代表字段end的节点。 |
| [FacingIdentificationMark](../../aspose.words.fields/fieldbarcode/facingidentificationmark/) { get; set; } | 获取或设置要插入的正面识别标记 (FIM) 的类型。 |
| [Format](../../aspose.words.fields/field/format/) { get; } | 得到一个[`FieldFormat`](../fieldformat/)提供对字段格式的类型化访问的对象。 |
| [IsBookmark](../../aspose.words.fields/fieldbarcode/isbookmark/) { get; set; } | 获取或设置是否[`PostalAddress`](./postaladdress/)是书签的名称。 |
| [IsDirty](../../aspose.words.fields/field/isdirty/) { get; set; } | 获取或设置字段的当前结果是否由于对文档的其他修改而不再正确（陈旧）。 |
| [IsLocked](../../aspose.words.fields/field/islocked/) { get; set; } | 获取或设置字段是否被锁定（不应重新计算其结果）。 |
| [IsUSPostalAddress](../../aspose.words.fields/fieldbarcode/isuspostaladdress/) { get; set; } | 获取或设置是否[`PostalAddress`](./postaladdress/)是美国邮政地址。 |
| [LocaleId](../../aspose.words.fields/field/localeid/) { get; set; } | 获取或设置字段的LCID。 |
| [PostalAddress](../../aspose.words.fields/fieldbarcode/postaladdress/) { get; set; } | 获取或设置用于生成条形码的邮政地址或引用它的书签的名称。 |
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

### 评论

以美国邮政服务使用的机器可读地址形式插入邮政条形码。

### 例子

演示如何使用 BARCODE 字段以条形码的形式显示美国邮政编码。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln();

// 下面是使用 BARCODE 字段将自定义值显示为条形码的两种方法。
// 1 - 存储条形码将显示在 PostalAddress 属性中的值：
FieldBarcode field = (FieldBarcode)builder.InsertField(FieldType.FieldBarcode, true);

// 此值必须是有效的邮政编码。
field.PostalAddress = "96801";
field.IsUSPostalAddress = true;
field.FacingIdentificationMark = "C";

Assert.AreEqual(" BARCODE  96801 \\u \\f C", field.GetFieldCode());

builder.InsertBreak(BreakType.LineBreak);

// 2 - 引用存储此条形码将显示的值的书签：
field = (FieldBarcode)builder.InsertField(FieldType.FieldBarcode, true);
field.PostalAddress = "BarcodeBookmark";
field.IsBookmark = true;

Assert.AreEqual(" BARCODE  BarcodeBookmark \\b", field.GetFieldCode());

// BARCODE 字段在其 PostalAddress 属性中引用的书签
// 除了有效的邮政编码之外，不需要包含任何内容。
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("BarcodeBookmark");
builder.Writeln("968877");
builder.EndBookmark("BarcodeBookmark");

doc.Save(ArtifactsDir + "Field.BARCODE.docx");
```

### 也可以看看

* class [Field](../field/)
* 命名空间 [Aspose.Words.Fields](../../aspose.words.fields/)
* 部件 [Aspose.Words](../../)


