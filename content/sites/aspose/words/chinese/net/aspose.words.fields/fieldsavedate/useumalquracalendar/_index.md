---
title: FieldSaveDate.UseUmAlQuraCalendar
second_title: Aspose.Words for .NET API 参考
description: FieldSaveDate 财产. 获取或设置是否使用 UmalQura 日历
type: docs
weight: 40
url: /zh/net/aspose.words.fields/fieldsavedate/useumalquracalendar/
---
## FieldSaveDate.UseUmAlQuraCalendar property

获取或设置是否使用 Um-al-Qura 日历。

```csharp
public bool UseUmAlQuraCalendar { get; set; }
```

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

* class [FieldSaveDate](../)
* 命名空间 [Aspose.Words.Fields](../../fieldsavedate/)
* 部件 [Aspose.Words](../../../)


