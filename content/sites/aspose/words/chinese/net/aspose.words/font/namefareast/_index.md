---
title: Font.NameFarEast
second_title: Aspose.Words for .NET API 参考
description: Font 财产. 返回或设置东亚字体名称
type: docs
weight: 260
url: /zh/net/aspose.words/font/namefareast/
---
## Font.NameFarEast property

返回或设置东亚字体名称。

```csharp
public string NameFarEast { get; set; }
```

### 例子

展示如何以远东语言插入和格式化文本。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 指定文档构建器将应用于其插入的任何文本的字体设置。
builder.Font.Name = "Courier New";
builder.Font.LocaleId = new CultureInfo("en-US", false).LCID;

// 为我们的字体和语言环境命名“FarEast”等价物。
// 如果构建器使用此字体配置插入亚洲字符，则每次运行包含
// 这些字符将使用“FarEast”字体/区域设置而不是默认值来显示它们。
// 当西方字体没有亚洲字符的理想表示时，这可能很有用。
builder.Font.NameFarEast = "SimSun";
builder.Font.LocaleIdFarEast = new CultureInfo("zh-CN", false).LCID;

// 此文本将以默认字体/区域设置显示。
builder.Writeln("Hello world!");

// 由于这些是亚洲字符，本次运行将应用我们的“远东”字体/区域设置等效项。
builder.Writeln("你好世界");

doc.Save(ArtifactsDir + "Font.FarEast.docx");
```

### 也可以看看

* property [Name](../name/)
* class [Font](../)
* 命名空间 [Aspose.Words](../../font/)
* 部件 [Aspose.Words](../../../)


