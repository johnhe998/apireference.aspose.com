---
title: FieldTemplate.IncludeFullPath
second_title: Aspose.Words for .NET API 参考
description: FieldTemplate 财产. 获取或设置是否包含完整的文件路径名
type: docs
weight: 20
url: /zh/net/aspose.words.fields/fieldtemplate/includefullpath/
---
## FieldTemplate.IncludeFullPath property

获取或设置是否包含完整的文件路径名。

```csharp
public bool IncludeFullPath { get; set; }
```

### 例子

演示如何使用 TEMPLATE 字段来显示文档模板的本地文件系统位置。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 我们可以通过字段设置模板名称。当“doc.AttachedTemplate”为空时使用此属性。
// 如果此属性为空，则使用默认模板文件名“Normal.dotm”。
doc.FieldOptions.TemplateName = string.Empty;

FieldTemplate field = (FieldTemplate)builder.InsertField(FieldType.FieldTemplate, false);
Assert.AreEqual(" TEMPLATE ", field.GetFieldCode());

builder.Writeln();
field = (FieldTemplate)builder.InsertField(FieldType.FieldTemplate, false);
field.IncludeFullPath = true;

Assert.AreEqual(" TEMPLATE  \\p", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.TEMPLATE.docx");
```

### 也可以看看

* class [FieldTemplate](../)
* 命名空间 [Aspose.Words.Fields](../../fieldtemplate/)
* 部件 [Aspose.Words](../../../)


