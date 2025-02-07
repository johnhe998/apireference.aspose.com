---
title: FieldOptions.FileName
second_title: Aspose.Words for .NET API 参考
description: FieldOptions 财产. 获取或设置文档的文件名
type: docs
weight: 120
url: /zh/net/aspose.words.fields/fieldoptions/filename/
---
## FieldOptions.FileName property

获取或设置文档的文件名。

```csharp
public string FileName { get; set; }
```

### 评论

该属性由[`FieldFileName`](../../fieldfilename/)具有更高优先级的字段[`OriginalFileName`](../../../aspose.words/document/originalfilename/)财产。

### 例子

演示如何使用 FieldOptions 覆盖 FILENAME 字段的默认值。

```csharp
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToDocumentEnd();
builder.Writeln();

// 这个 FILENAME 字段将显示我们加载的文档的本地系统文件名。
FieldFileName field = (FieldFileName)builder.InsertField(FieldType.FieldFileName, true);
field.Update();

Assert.AreEqual(" FILENAME ", field.GetFieldCode());
Assert.AreEqual("Document.docx", field.Result);

builder.Writeln();

// 默认情况下，FILENAME 字段显示文件名，但不显示其完整的本地文件系统路径。
// 我们可以设置一个标志来让它显示完整的文件路径。
field = (FieldFileName)builder.InsertField(FieldType.FieldFileName, true);
field.IncludeFullPath = true;
field.Update();

Assert.AreEqual(MyDir + "Document.docx", field.Result);

// 我们也可以为这个属性设置一个值
// 覆盖 FILENAME 字段显示的值。
doc.FieldOptions.FileName = "FieldOptions.FILENAME.docx";
field.Update();

Assert.AreEqual(" FILENAME  \\p", field.GetFieldCode());
Assert.AreEqual("FieldOptions.FILENAME.docx", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + doc.FieldOptions.FileName);
```

### 也可以看看

* class [FieldOptions](../)
* 命名空间 [Aspose.Words.Fields](../../fieldoptions/)
* 部件 [Aspose.Words](../../../)


