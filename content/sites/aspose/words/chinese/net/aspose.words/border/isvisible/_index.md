---
title: Border.IsVisible
second_title: Aspose.Words for .NET API 参考
description: Border 财产. 如果 LineStyle 不是 LineStyle.None则返回 true
type: docs
weight: 30
url: /zh/net/aspose.words/border/isvisible/
---
## Border.IsVisible property

如果 LineStyle 不是 LineStyle.None，则返回 true。

```csharp
public bool IsVisible { get; }
```

### 例子

演示如何从段落中删除边框。

```csharp
Document doc = new Document(MyDir + "Borders.docx");

// 每个段落都有一组单独的边框。
// 我们可以通过段落格式对象访问这些边框的外观设置。
BorderCollection borders = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Borders;

Assert.AreEqual(Color.Red.ToArgb(), borders[0].Color.ToArgb());
Assert.AreEqual(3.0d, borders[0].LineWidth);
Assert.AreEqual(LineStyle.Single, borders[0].LineStyle);
Assert.True(borders[0].IsVisible);

// 我们可以通过运行 ClearFormatting 方法立即删除边框。 
// 在段落的每个边框上运行此方法将删除其所有边框。
foreach (Border border in borders)
    border.ClearFormatting();

Assert.AreEqual(Color.Empty.ToArgb(), borders[0].Color.ToArgb());
Assert.AreEqual(0.0d, borders[0].LineWidth);
Assert.AreEqual(LineStyle.None, borders[0].LineStyle);
Assert.IsFalse(borders[0].IsVisible);

doc.Save(ArtifactsDir + "Border.ClearFormatting.docx");
```

### 也可以看看

* class [Border](../)
* 命名空间 [Aspose.Words](../../border/)
* 部件 [Aspose.Words](../../../)


