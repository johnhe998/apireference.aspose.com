---
title: ViewOptions.ZoomPercent
second_title: Aspose.Words for .NET API 参考
description: ViewOptions 财产. 获取或设置要查看文档的百分比10 到 500 之间
type: docs
weight: 50
url: /zh/net/aspose.words.settings/viewoptions/zoompercent/
---
## ViewOptions.ZoomPercent property

获取或设置要查看文档的百分比（10 到 500 之间）。

```csharp
public int ZoomPercent { get; set; }
```

### 评论

如果 value 为 0，则此属性使用 100，否则如果 value 小于 10 或大于 ，则此属性将抛出。

虽然 Aspose.Words 能够读写这个选项，但它的使用是特定于应用程序的。 例如 MS Word 2013 不尊重此选项的值。

### 例子

显示如何设置自定义缩放系数，旧版本的 Microsoft Word 将在加载时应用于文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

Assert.AreEqual(ZoomType.Custom, doc.ViewOptions.ZoomType);
Assert.AreEqual(ZoomType.None, doc.ViewOptions.ZoomType);

doc.Save(ArtifactsDir + "ViewOptions.SetZoomPercentage.doc");
```

### 也可以看看

* class [ViewOptions](../)
* 命名空间 [Aspose.Words.Settings](../../viewoptions/)
* 部件 [Aspose.Words](../../../)


