---
title: FindReplaceOptions.LegacyMode
second_title: Aspose.Words for .NET API 参考
description: FindReplaceOptions 财产. 获取或设置一个布尔值指示使用旧的查找/替换算法
type: docs
weight: 110
url: /zh/net/aspose.words.replacing/findreplaceoptions/legacymode/
---
## FindReplaceOptions.LegacyMode property

获取或设置一个布尔值，指示使用旧的查找/替换算法。

```csharp
public bool LegacyMode { get; set; }
```

### 评论

如果您需要与引入高级查找/替换功能之前完全相同的行为，请使用此标志。 请注意，旧算法不支持高级功能，例如用中断替换、应用格式等。

### 例子

展示如何识别和使用替换模式中的替换。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Jason gave money to Paul.");

Regex regex = new Regex(@"([A-z]+) gave money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions();
options.UseSubstitutions = true;

// 使用 legacy 模式不支持很多高级功能，所以我们需要将其设置为 'false'。
options.LegacyMode = false;

doc.Range.Replace(regex, @"$2 took money from $1", options);

Assert.AreEqual(doc.GetText(), "Paul took money from Jason.\f");
```

### 也可以看看

* class [FindReplaceOptions](../)
* 命名空间 [Aspose.Words.Replacing](../../findreplaceoptions/)
* 部件 [Aspose.Words](../../../)


