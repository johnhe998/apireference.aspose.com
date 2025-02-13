---
title: Class SaveOutputParameters
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Saving.SaveOutputParameters 班级. 该对象在保存文档后返回给调用者并包含在保存操作期间生成或计算的 的附加信息调用者可以使用或忽略这个对象
type: docs
weight: 5310
url: /zh/net/aspose.words.saving/saveoutputparameters/
---
## SaveOutputParameters class

该对象在保存文档后返回给调用者，并包含在保存操作期间生成或计算的 的附加信息。调用者可以使用或忽略这个对象。

```csharp
public class SaveOutputParameters
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [ContentType](../../aspose.words.saving/saveoutputparameters/contenttype/) { get; } | 返回标识已保存文档类型的 Content-Type 字符串（Internet 媒体类型）。 |

### 例子

显示如何访问文档保存操作的输出参数。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// 保存文档后，我们可以访问新创建的输出文档的 Internet Media Type（MIME 类型）。
SaveOutputParameters parameters = doc.Save(ArtifactsDir + "Document.SaveOutputParameters.doc");

Assert.AreEqual("application/msword", parameters.ContentType);

// 此属性根据保存格式而变化。
parameters = doc.Save(ArtifactsDir + "Document.SaveOutputParameters.pdf");

Assert.AreEqual("application/pdf", parameters.ContentType);
```

### 也可以看看

* 命名空间 [Aspose.Words.Saving](../../aspose.words.saving/)
* 部件 [Aspose.Words](../../)


