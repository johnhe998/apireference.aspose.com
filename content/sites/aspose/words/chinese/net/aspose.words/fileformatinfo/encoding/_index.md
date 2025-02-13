---
title: FileFormatInfo.Encoding
second_title: Aspose.Words for .NET API 参考
description: FileFormatInfo 财产. 如果适用于当前文档格式则获取检测到的编码 目前仅检测 HTML 文档的编码
type: docs
weight: 10
url: /zh/net/aspose.words/fileformatinfo/encoding/
---
## FileFormatInfo.Encoding property

如果适用于当前文档格式，则获取检测到的编码。 目前仅检测 HTML 文档的编码。

```csharp
public Encoding Encoding { get; }
```

### 例子

展示如何检测 html 文件中的编码。

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(MyDir + "Document.html");

Assert.AreEqual(LoadFormat.Html, info.LoadFormat);

// Encoding 属性仅在我们为 html 文档创建 FileFormatInfo 对象时使用。
Assert.AreEqual("Western European (Windows)", info.Encoding.EncodingName);
Assert.AreEqual(1252, info.Encoding.CodePage);
```

### 也可以看看

* class [FileFormatInfo](../)
* 命名空间 [Aspose.Words](../../fileformatinfo/)
* 部件 [Aspose.Words](../../../)


