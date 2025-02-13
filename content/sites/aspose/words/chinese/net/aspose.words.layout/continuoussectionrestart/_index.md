---
title: Enum ContinuousSectionRestart
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Layout.ContinuousSectionRestart 枚举. 表示在重新开始页码的连续部分中计算页码时的不同行为
type: docs
weight: 3100
url: /zh/net/aspose.words.layout/continuoussectionrestart/
---
## ContinuousSectionRestart enumeration

表示在重新开始页码的连续部分中计算页码时的不同行为。

```csharp
public enum ContinuousSectionRestart
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Always | `0` | 无论内容流如何，页码总是重新开始。 |
| FromNewPageOnly | `1` | 仅当节开始的页面上的节之前没有其他内容时，页码才会重新开始。 |

### 例子

显示如何控制连续部分中的页码。

```csharp
Document doc = new Document(MyDir + "Continuous section page numbering.docx");

// 默认情况下，Aspose.Words 行为与 Microsoft Word 2019 匹配。
// 如果您需要旧的 Aspose.Words 行为，重复 Microsoft Word 2016，请使用“ContinuousSectionRestart.FromNewPageOnly”。
// 只有在节开始的页面上的节之前没有其他内容时，才重新开始页码，
//因此编号将从第二页重置为2。
doc.LayoutOptions.ContinuousSectionPageNumberingRestart = ContinuousSectionRestart.FromNewPageOnly;
doc.UpdatePageLayout();

doc.Save(ArtifactsDir + "Layout.RestartPageNumberingInContinuousSection.pdf");
```

### 也可以看看

* 命名空间 [Aspose.Words.Layout](../../aspose.words.layout/)
* 部件 [Aspose.Words](../../)


