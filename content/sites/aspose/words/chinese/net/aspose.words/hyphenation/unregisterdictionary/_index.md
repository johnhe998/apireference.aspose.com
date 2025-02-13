---
title: Hyphenation.UnregisterDictionary
second_title: Aspose.Words for .NET API 参考
description: Hyphenation 方法. 取消注册指定语言的断字字典
type: docs
weight: 50
url: /zh/net/aspose.words/hyphenation/unregisterdictionary/
---
## Hyphenation.UnregisterDictionary method

取消注册指定语言的断字字典。

这与注册 Null 字典不同。取消注册字典启用指定语言的回调。

```csharp
public static void UnregisterDictionary(string language)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| language | String | 语言名称，例如“en-US”。有关详细信息，请参阅 .NET 文档以了解“文化名称”和 RFC 4646。 |

### 例子

显示如何注册断字字典。

```csharp
// 断字字典包含定义字典语言的断字规则的字符串列表。
// 当文档包含可以拆分单词并在下一行继续的文本行时，
// 断字将在字典的字符串列表中查找该单词的子字符串。
// 如果字典包含子字符串，则断字会将单词分成两行
// 通过子字符串并在前半部分添加连字符。
// 将本地文件系统中的字典文件注册到“de-CH”语言环境。
Hyphenation.RegisterDictionary("de-CH", MyDir + "hyph_de_CH.dic");

Assert.True(Hyphenation.IsDictionaryRegistered("de-CH"));

// 打开一个包含与我们的字典相匹配的语言环境的文本的文档，
// 并将其保存为固定页面保存格式。该文档中的文本将被连字符。
Document doc = new Document(MyDir + "German text.docx");

Assert.True(doc.FirstSection.Body.FirstParagraph.Runs.OfType<Run>().All(
    r => r.Font.LocaleId == new CultureInfo("de-CH").LCID));

doc.Save(ArtifactsDir + "Hyphenation.Dictionary.Registered.pdf");

// 注销字典后重新加载文档，
// 并将其保存到另一个没有连字符的 PDF。
Hyphenation.UnregisterDictionary("de-CH");

Assert.False(Hyphenation.IsDictionaryRegistered("de-CH"));

doc = new Document(MyDir + "German text.docx");
doc.Save(ArtifactsDir + "Hyphenation.Dictionary.Unregistered.pdf");
```

### 也可以看看

* class [Hyphenation](../)
* 命名空间 [Aspose.Words](../../hyphenation/)
* 部件 [Aspose.Words](../../../)


