---
title: FieldKeywords.Text
second_title: Aspose.Words for .NET API 参考
description: FieldKeywords 财产. 获取或设置关键字的文本
type: docs
weight: 20
url: /zh/net/aspose.words.fields/fieldkeywords/text/
---
## FieldKeywords.Text property

获取或设置关键字的文本。

```csharp
public string Text { get; set; }
```

### 例子

显示插入 KEYWORDS 字段。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 添加一些关键字，在文件资源管理器中也称为“标签”。
doc.BuiltInDocumentProperties.Keywords = "Keyword1, Keyword2";

// KEYWORDS 字段显示此属性的值。
FieldKeywords field = (FieldKeywords)builder.InsertField(FieldType.FieldKeyword, true);
field.Update();

Assert.AreEqual(" KEYWORDS ", field.GetFieldCode());
Assert.AreEqual("Keyword1, Keyword2", field.Result);

// 为字段的 Text 属性设置一个值，
// 然后更新字段也会用新值覆盖相应的内置属性。
field.Text = "OverridingKeyword";
field.Update();

Assert.AreEqual(" KEYWORDS  OverridingKeyword", field.GetFieldCode());
Assert.AreEqual("OverridingKeyword", field.Result);
Assert.AreEqual("OverridingKeyword", doc.BuiltInDocumentProperties.Keywords);

doc.Save(ArtifactsDir + "Field.KEYWORDS.docx");
```

### 也可以看看

* class [FieldKeywords](../)
* 命名空间 [Aspose.Words.Fields](../../fieldkeywords/)
* 部件 [Aspose.Words](../../../)


