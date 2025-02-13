---
title: Field.Result
second_title: Aspose.Words for .NET API 参考
description: Field 财产. 获取或设置字段分隔符和字段结尾之间的文本
type: docs
weight: 70
url: /zh/net/aspose.words.fields/field/result/
---
## Field.Result property

获取或设置字段分隔符和字段结尾之间的文本。

```csharp
public string Result { get; set; }
```

### 例子

演示如何使用域代码将域插入到文档中。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Field field = builder.InsertField("DATE \\@ \"dddd, MMMM dd, yyyy\"");

Assert.AreEqual(FieldType.FieldDate, field.Type);
Assert.AreEqual("DATE \\@ \"dddd, MMMM dd, yyyy\"", field.GetFieldCode());

// InsertField 方法的这个重载会自动更新插入的字段。
Assert.That(DateTime.Parse(field.Result), Is.EqualTo(DateTime.Today).Within(1).Days);
```

### 也可以看看

* class [Field](../)
* 命名空间 [Aspose.Words.Fields](../../field/)
* 部件 [Aspose.Words](../../../)


