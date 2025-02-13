---
title: PageSetup.BorderAppliesTo
second_title: Aspose.Words for .NET API 参考
description: PageSetup 财产. 指定打印页面边框的页面
type: docs
weight: 30
url: /zh/net/aspose.words/pagesetup/borderappliesto/
---
## PageSetup.BorderAppliesTo property

指定打印页面边框的页面。

```csharp
public PageBorderAppliesTo BorderAppliesTo { get; set; }
```

### 例子

展示如何在第一页的顶部创建一个宽的蓝色边框。

```csharp
Document doc = new Document();

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.BorderAlwaysInFront = false;
pageSetup.BorderDistanceFrom = PageBorderDistanceFrom.PageEdge;
pageSetup.BorderAppliesTo = PageBorderAppliesTo.FirstPage;

Border border = pageSetup.Borders[BorderType.Top];
border.LineStyle = LineStyle.Single;
border.LineWidth = 30;
border.Color = Color.Blue;
border.DistanceFromText = 0;

doc.Save(ArtifactsDir + "PageSetup.PageBorderProperties.docx");
```

### 也可以看看

* enum [PageBorderAppliesTo](../../pageborderappliesto/)
* class [PageSetup](../)
* 命名空间 [Aspose.Words](../../pagesetup/)
* 部件 [Aspose.Words](../../../)


