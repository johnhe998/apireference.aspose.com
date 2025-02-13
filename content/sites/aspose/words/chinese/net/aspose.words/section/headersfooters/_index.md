---
title: Section.HeadersFooters
second_title: Aspose.Words for .NET API 参考
description: Section 财产. 提供对节的页眉和页脚节点的访问
type: docs
weight: 30
url: /zh/net/aspose.words/section/headersfooters/
---
## Section.HeadersFooters property

提供对节的页眉和页脚节点的访问。

```csharp
public HeaderFooterCollection HeadersFooters { get; }
```

### 例子

显示如何替换文档页脚中的文本。

```csharp
Document doc = new Document(MyDir + "Footer.docx");

HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];

FindReplaceOptions options = new FindReplaceOptions
{
    MatchCase = false,
    FindWholeWordsOnly = false
};

int currentYear = DateTime.Now.Year;
footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", $"Copyright (C) {currentYear} by Aspose Pty Ltd.", options);

doc.Save(ArtifactsDir + "HeaderFooter.ReplaceText.docx");
```

显示如何从文档中删除所有页脚。

```csharp
Document doc = new Document(MyDir + "Header and footer types.docx");

// 遍历每个部分并删除各种页脚。
foreach (Section section in doc.OfType<Section>())
{
    // 共有三种页脚和页眉类型。
    // 1 - “第一个”页眉/页脚，仅出现在部分的第一页上。
    HeaderFooter footer = section.HeadersFooters[HeaderFooterType.FooterFirst];
    footer?.Remove();

    // 2 - “主要”页眉/页脚，出现在奇数页上。
    footer = section.HeadersFooters[HeaderFooterType.FooterPrimary];
    footer?.Remove();

     // 3 - “偶数”页眉/页脚，出现在偶数页上。
    footer = section.HeadersFooters[HeaderFooterType.FooterEven];
    footer?.Remove();

    Assert.AreEqual(0, section.HeadersFooters.Count(hf => !((HeaderFooter)hf).IsHeader));
}

doc.Save(ArtifactsDir + "HeaderFooter.RemoveFooters.docx");
```

### 也可以看看

* class [HeaderFooterCollection](../../headerfootercollection/)
* class [Section](../)
* 命名空间 [Aspose.Words](../../section/)
* 部件 [Aspose.Words](../../../)


