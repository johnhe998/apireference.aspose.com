---
title: Document.RemovePersonalInformation
second_title: Aspose.Words for .NET API 参考
description: Document 财产. 获取或设置一个标志表明 Microsoft Word 将在保存文档时从注释修订和 文档属性中删除所有用户信息
type: docs
weight: 320
url: /zh/net/aspose.words/document/removepersonalinformation/
---
## Document.RemovePersonalInformation property

获取或设置一个标志，表明 Microsoft Word 将在保存文档时从注释、修订和 文档属性中删除所有用户信息。

```csharp
public bool RemovePersonalInformation { get; set; }
```

### 例子

显示如何在手动保存期间启用个人信息的删除。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入一些带有个人信息的内容。
doc.BuiltInDocumentProperties.Author = "John Doe";
doc.BuiltInDocumentProperties.Company = "Placeholder Inc.";

doc.StartTrackRevisions(doc.BuiltInDocumentProperties.Author, DateTime.Now);
builder.Write("Hello world!");
doc.StopTrackRevisions();

// 这个标志相当于 File ->选项->信任中心 ->信任中心设置... ->
// 隐私选项 -> Microsoft Word 中的“保存时从文件属性中删除个人信息”。
doc.RemovePersonalInformation = saveWithoutPersonalInfo;

// 此选项在使用 Aspose.Words 进行的保存操作期间不会生效。
// 当我们使用 Microsoft Word 手动保存时，个人数据将从我们的文档中删除并设置标志。
doc.Save(ArtifactsDir + "Document.RemovePersonalInformation.docx");
doc = new Document(ArtifactsDir + "Document.RemovePersonalInformation.docx");

Assert.AreEqual(saveWithoutPersonalInfo, doc.RemovePersonalInformation);
Assert.AreEqual("John Doe", doc.BuiltInDocumentProperties.Author);
Assert.AreEqual("Placeholder Inc.", doc.BuiltInDocumentProperties.Company);
Assert.AreEqual("John Doe", doc.Revisions[0].Author);
```

### 也可以看看

* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)


