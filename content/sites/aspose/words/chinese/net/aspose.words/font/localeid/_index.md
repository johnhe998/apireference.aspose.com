---
title: Font.LocaleId
second_title: Aspose.Words for .NET API 参考
description: Font 财产. 获取或设置格式化字符的区域设置标识符语言
type: docs
weight: 200
url: /zh/net/aspose.words/font/localeid/
---
## Font.LocaleId property

获取或设置格式化字符的区域设置标识符（语言）。

```csharp
public int LocaleId { get; set; }
```

### 评论

有关区域设置标识符的列表，请参阅 https://msdn.microsoft.com/en-us/library/cc233965.aspx

### 例子

展示如何设置我们使用文档构建器添加的文本的语言环境。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 如果我们将字体的区域设置为英语并插入一些俄语文本，
// 英语区域拼写检查器将无法识别文本并将其检测为拼写错误。
builder.Font.LocaleId = new CultureInfo("en-US", false).LCID;
builder.Writeln("Привет!");

// 为我们要添加的文本设置一个匹配的语言环境，以应用适当的拼写检查器。
builder.Font.LocaleId = new CultureInfo("ru-RU", false).LCID;
builder.Writeln("Привет!");

doc.Save(ArtifactsDir + "Font.LocaleId.docx");
```

### 也可以看看

* class [Font](../)
* 命名空间 [Aspose.Words](../../font/)
* 部件 [Aspose.Words](../../../)


