---
title: FieldOptions.PreProcessCulture
second_title: Aspose.Words for .NET API 参考
description: FieldOptions 财产. 获取或设置区域性以预处理字段值
type: docs
weight: 150
url: /zh/net/aspose.words.fields/fieldoptions/preprocessculture/
---
## FieldOptions.PreProcessCulture property

获取或设置区域性以预处理字段值。

```csharp
public CultureInfo PreProcessCulture { get; set; }
```

### 评论

目前这个属性只影响[`FieldDocProperty`](../../fielddocproperty/)场地。

默认值为 **无效的** .当此属性设置为 **无效的**， 这[`FieldDocProperty`](../../fielddocproperty/)字段的值是 preprocessed ，文化由[`FieldUpdateCultureSource`](../fieldupdateculturesource/)财产。

### 例子

显示如何设置预处理区域性。

```csharp
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// 设置某些字段将根据其设置显示值的区域性。
doc.FieldOptions.PreProcessCulture = new CultureInfo("de-DE");

Field field = builder.InsertField(" DOCPROPERTY CreateTime");

// DOCPROPERTY 字段将根据预处理区域性显示其结果
// 我们已经设置为德语。该字段将使用“dd.mm.yyyy hh:mm”格式显示日期/时间。
Assert.IsTrue(Regex.Match(field.Result, @"\d{2}[.]\d{2}[.]\d{4} \d{2}[:]\d{2}").Success);

doc.FieldOptions.PreProcessCulture = CultureInfo.InvariantCulture;
field.Update();

// 切换到不变区域性后，DOCPROPERTY 字段将使用“mm/dd/yyyy hh:mm”格式。
Assert.IsTrue(Regex.Match(field.Result, @"\d{2}[/]\d{2}[/]\d{4} \d{2}[:]\d{2}").Success);
```

### 也可以看看

* class [FieldOptions](../)
* 命名空间 [Aspose.Words.Fields](../../fieldoptions/)
* 部件 [Aspose.Words](../../../)


