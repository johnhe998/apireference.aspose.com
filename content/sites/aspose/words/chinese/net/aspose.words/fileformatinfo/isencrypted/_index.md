---
title: FileFormatInfo.IsEncrypted
second_title: Aspose.Words for .NET API 参考
description: FileFormatInfo 财产. 如果文档已加密并且需要密码才能打开则返回 true
type: docs
weight: 30
url: /zh/net/aspose.words/fileformatinfo/isencrypted/
---
## FileFormatInfo.IsEncrypted property

如果文档已加密并且需要密码才能打开，则返回 true。

```csharp
public bool IsEncrypted { get; }
```

### 评论

该属性的存在是为了帮助您对加密文档和未加密文档进行排序。 如果您尝试使用 Aspose.Words 加载加密文档而不提供密码，则会引发 异常。您可以使用此属性来检测文档是否需要密码 并在加载文档之前执行一些操作，例如提示用户输入密码。

### 例子

演示如何使用 FileFormatUtil 类来检测文档格式和加密。

```csharp
Document doc = new Document();

// 配置一个 SaveOptions 对象来加密文档
// 保存时输入密码，然后保存文档。
OdtSaveOptions saveOptions = new OdtSaveOptions(SaveFormat.Odt);
saveOptions.Password = "MyPassword";

doc.Save(ArtifactsDir + "File.DetectDocumentEncryption.odt", saveOptions);

// 验证我们文档的文件类型，以及它的加密状态。
FileFormatInfo info = FileFormatUtil.DetectFileFormat(ArtifactsDir + "File.DetectDocumentEncryption.odt");

Assert.AreEqual(".odt", FileFormatUtil.LoadFormatToExtension(info.LoadFormat));
Assert.True(info.IsEncrypted);
```

### 也可以看看

* class [FileFormatInfo](../)
* 命名空间 [Aspose.Words](../../fileformatinfo/)
* 部件 [Aspose.Words](../../../)


