---
title: DocSaveOptions.SaveRoutingSlip
second_title: Aspose.Words for .NET API 参考
description: DocSaveOptions 财产. 什么时候错误的  RoutingSlip 数据不保存到输出文档 默认值为 真的.
type: docs
weight: 60
url: /zh/net/aspose.words.saving/docsaveoptions/saveroutingslip/
---
## DocSaveOptions.SaveRoutingSlip property

什么时候`错误的` , RoutingSlip 数据不保存到输出文档。 默认值为 **真的**.

```csharp
public bool SaveRoutingSlip { get; set; }
```

### 例子

显示如何为旧版 Microsoft Word 格式设置保存选项。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Hello world!");

DocSaveOptions options = new DocSaveOptions(SaveFormat.Doc);

// 设置密码以保护 Microsoft Word 或 Aspose.Words 加载文档。
// 请注意，这不会以任何方式加密文档的内容。
options.Password = "MyPassword";

// 如果文档包含路由单，我们可以通过将此标志设置为 true 来在保存时保留它。
options.SaveRoutingSlip = true;

doc.Save(ArtifactsDir + "DocSaveOptions.SaveAsDoc.doc", options);

// 为了能够加载文档，
// 我们需要将我们在 DocSaveOptions 对象中指定的密码应用到 LoadOptions 对象中。
Assert.Throws<IncorrectPasswordException>(() => doc = new Document(ArtifactsDir + "DocSaveOptions.SaveAsDoc.doc"));

LoadOptions loadOptions = new LoadOptions("MyPassword");
doc = new Document(ArtifactsDir + "DocSaveOptions.SaveAsDoc.doc", loadOptions);

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### 也可以看看

* class [DocSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../docsaveoptions/)
* 部件 [Aspose.Words](../../../)


