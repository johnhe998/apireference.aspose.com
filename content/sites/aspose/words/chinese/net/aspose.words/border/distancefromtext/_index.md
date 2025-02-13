---
title: Border.DistanceFromText
second_title: Aspose.Words for .NET API 参考
description: Border 财产. 获取或设置边框与文本或页面边缘的距离以磅为单位
type: docs
weight: 20
url: /zh/net/aspose.words/border/distancefromtext/
---
## Border.DistanceFromText property

获取或设置边框与文本或页面边缘的距离（以磅为单位）。

```csharp
public double DistanceFromText { get; set; }
```

### 评论

没有影响，表格单元格的边框将自动重置为零。

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

* class [Border](../)
* 命名空间 [Aspose.Words](../../border/)
* 部件 [Aspose.Words](../../../)


