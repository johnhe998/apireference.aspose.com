---
title: FieldDate.UseLastFormat
second_title: Aspose.Words for .NET API 参考
description: FieldDate 财产. 获取或设置在插入新的 DATE 字段时是否使用宿主应用程序上次使用的格式
type: docs
weight: 20
url: /zh/net/aspose.words.fields/fielddate/uselastformat/
---
## FieldDate.UseLastFormat property

获取或设置在插入新的 DATE 字段时是否使用宿主应用程序上次使用的格式。

```csharp
public bool UseLastFormat { get; set; }
```

### 例子

演示如何使用 DATE 字段根据不同类型的日历显示日期。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 如果我们希望文档中的文本始终显示正确的日期，我们可以使用 DATE 字段。
// 以下是 DATE 字段可用于显示日期的三种文化日历。
// 1 - 伊斯兰农历：
FieldDate field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseLunarCalendar = true;
Assert.AreEqual(" DATE  \\h", field.GetFieldCode());
builder.Writeln();

// 2 - Umm al-Qura 日历：
field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseUmAlQuraCalendar = true;
Assert.AreEqual(" DATE  \\u", field.GetFieldCode());
builder.Writeln();

// 3 - 印度国历：
field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseSakaEraCalendar = true;
Assert.AreEqual(" DATE  \\s", field.GetFieldCode());
builder.Writeln();

// 插入一个 DATE 字段并将其日历类型设置为主机应用程序最后使用的日历类型。
// 在 Microsoft Word 中，类型将是 Insert -> 中最近使用的类型文本->日期和时间对话框。
field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseLastFormat = true;
Assert.AreEqual(" DATE  \\l", field.GetFieldCode());
builder.Writeln();

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.DATE.docx");
```

### 也可以看看

* class [FieldDate](../)
* 命名空间 [Aspose.Words.Fields](../../fielddate/)
* 部件 [Aspose.Words](../../../)


