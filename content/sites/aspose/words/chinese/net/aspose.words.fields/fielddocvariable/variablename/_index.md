---
title: FieldDocVariable.VariableName
second_title: Aspose.Words for .NET API 参考
description: FieldDocVariable 财产. 获取或设置要检索的文档变量的名称
type: docs
weight: 20
url: /zh/net/aspose.words.fields/fielddocvariable/variablename/
---
## FieldDocVariable.VariableName property

获取或设置要检索的文档变量的名称。

```csharp
public string VariableName { get; set; }
```

### 例子

演示如何使用 DOCPROPERTY 字段来显示文档属性和变量。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 下面是使用 DOCPROPERTY 字段的两种方式。
// 1 - 显示一个内置属性：
// 为“Category”内置属性设置自定义值，然后插入引用它的 DOCPROPERTY 字段。
doc.BuiltInDocumentProperties.Category = "My category";

FieldDocProperty fieldDocProperty = (FieldDocProperty)builder.InsertField(" DOCPROPERTY Category ");
fieldDocProperty.Update();

Assert.AreEqual(" DOCPROPERTY Category ", fieldDocProperty.GetFieldCode());
Assert.AreEqual("My category", fieldDocProperty.Result);

builder.InsertParagraph();

// 2 - 显示自定义文档变量：
// 定义一个自定义变量，然后使用 DOCPROPERTY 字段引用该变量。
Assert.That(doc.Variables, Is.Empty);
doc.Variables.Add("My variable", "My variable's value");

FieldDocVariable fieldDocVariable = (FieldDocVariable)builder.InsertField(FieldType.FieldDocVariable, true);
fieldDocVariable.VariableName = "My Variable";
fieldDocVariable.Update();

Assert.AreEqual(" DOCVARIABLE  \"My Variable\"", fieldDocVariable.GetFieldCode());
Assert.AreEqual("My variable's value", fieldDocVariable.Result);

doc.Save(ArtifactsDir + "Field.DOCPROPERTY.DOCVARIABLE.docx");
```

### 也可以看看

* class [FieldDocVariable](../)
* 命名空间 [Aspose.Words.Fields](../../fielddocvariable/)
* 部件 [Aspose.Words](../../../)


