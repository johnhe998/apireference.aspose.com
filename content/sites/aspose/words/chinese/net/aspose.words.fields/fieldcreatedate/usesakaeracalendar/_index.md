---
title: FieldCreateDate.UseSakaEraCalendar
second_title: Aspose.Words for .NET API 参考
description: FieldCreateDate 财产. 获取或设置是否使用Saka Era日历
type: docs
weight: 30
url: /zh/net/aspose.words.fields/fieldcreatedate/usesakaeracalendar/
---
## FieldCreateDate.UseSakaEraCalendar property

获取或设置是否使用Saka Era日历。

```csharp
public bool UseSakaEraCalendar { get; set; }
```

### 例子

显示如何使用 CREATEDATE 字段来显示文档的创建日期/时间。

```csharp
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.Writeln(" Date this document was created:");

// 我们可以使用 CREATEDATE 字段来显示文档创建的日期和时间。
// 下面是三种不同的日历类型，根据这些类型，CREATEDATE 字段可以显示日期/时间。
// 1 - 伊斯兰农历：
builder.Write("According to the Lunar Calendar - ");
FieldCreateDate field = (FieldCreateDate)builder.InsertField(FieldType.FieldCreateDate, true);
field.UseLunarCalendar = true;

Assert.AreEqual(" CREATEDATE  \\h", field.GetFieldCode());

// 2 - Umm al-Qura 日历：
builder.Write("\nAccording to the Umm al-Qura Calendar - ");
field = (FieldCreateDate)builder.InsertField(FieldType.FieldCreateDate, true);
field.UseUmAlQuraCalendar = true;

Assert.AreEqual(" CREATEDATE  \\u", field.GetFieldCode());

// 3 - 印度国历：
builder.Write("\nAccording to the Indian National Calendar - ");
field = (FieldCreateDate)builder.InsertField(FieldType.FieldCreateDate, true);
field.UseSakaEraCalendar = true;

Assert.AreEqual(" CREATEDATE  \\s", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.CREATEDATE.docx");
```

### 也可以看看

* class [FieldCreateDate](../)
* 命名空间 [Aspose.Words.Fields](../../fieldcreatedate/)
* 部件 [Aspose.Words](../../../)


