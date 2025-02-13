---
title: FieldOptions.UseInvariantCultureNumberFormat
second_title: Aspose.Words for .NET API 参考
description: FieldOptions 财产. 获取或设置数值格式是否使用不变区域性解析
type: docs
weight: 190
url: /zh/net/aspose.words.fields/fieldoptions/useinvariantculturenumberformat/
---
## FieldOptions.UseInvariantCultureNumberFormat property

获取或设置数值格式是否使用不变区域性解析

```csharp
public bool UseInvariantCultureNumberFormat { get; set; }
```

### 评论

当此属性设置为 **真的** 数字格式取自不变的文化。

当此属性设置为 **错误的** 数字格式取自当前线程的文化。

默认值为 **错误的**.

### 例子

显示如何根据不变的文化格式化数字。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
Field field = builder.InsertField(" = 1234567,89 \\# $#,###,###.##");
field.Update();

// 有时，在某些文化下，字段的数字格式可能不正确。 
Assert.IsFalse(doc.FieldOptions.UseInvariantCultureNumberFormat);
Assert.AreEqual("$1234567,89 .     ", field.Result);

// 为了解决这个问题，我们可以改变整个线程的文化。
// 解决这个问题的另一种方法是设置这个标志，
// 它使所有字段在格式化数字时都使用不变的文化。
// 这种方式允许我们避免改变整个线程的文化。
doc.FieldOptions.UseInvariantCultureNumberFormat = true;
field.Update();
Assert.AreEqual("$1.234.567,89", field.Result);
```

### 也可以看看

* class [FieldOptions](../)
* 命名空间 [Aspose.Words.Fields](../../fieldoptions/)
* 部件 [Aspose.Words](../../../)


