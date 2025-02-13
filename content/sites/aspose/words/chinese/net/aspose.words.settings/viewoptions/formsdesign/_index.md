---
title: ViewOptions.FormsDesign
second_title: Aspose.Words for .NET API 参考
description: ViewOptions 财产. 指定文档是否处于表单设计模式
type: docs
weight: 30
url: /zh/net/aspose.words.settings/viewoptions/formsdesign/
---
## ViewOptions.FormsDesign property

指定文档是否处于表单设计模式。

```csharp
public bool FormsDesign { get; set; }
```

### 评论

目前仅适用于 WordML 格式的文档。

### 例子

显示如何启用/禁用表单设计模式。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// 将“FormsDesign”属性设置为“false”以禁用表单设计模式。
// 将“FormsDesign”属性设置为“true”以启用表单设计模式。
doc.ViewOptions.FormsDesign = useFormsDesign;

doc.Save(ArtifactsDir + "ViewOptions.FormsDesign.xml");

Assert.AreEqual(useFormsDesign,
    File.ReadAllText(ArtifactsDir + "ViewOptions.FormsDesign.xml").Contains("<w:formsDesign />"));
```

### 也可以看看

* class [ViewOptions](../)
* 命名空间 [Aspose.Words.Settings](../../viewoptions/)
* 部件 [Aspose.Words](../../../)


