---
title: Class ViewOptions
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Settings.ViewOptions 班级. 提供控制文档在 Microsoft Word 中的显示方式的各种选项
type: docs
weight: 5650
url: /zh/net/aspose.words.settings/viewoptions/
---
## ViewOptions class

提供控制文档在 Microsoft Word 中的显示方式的各种选项。

```csharp
public class ViewOptions
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [DisplayBackgroundShape](../../aspose.words.settings/viewoptions/displaybackgroundshape/) { get; set; } | 控制打印布局视图中背景形状的显示。 |
| [DoNotDisplayPageBoundaries](../../aspose.words.settings/viewoptions/donotdisplaypageboundaries/) { get; set; } | 关闭文本顶部和页面顶部边缘之间空间的显示。 |
| [FormsDesign](../../aspose.words.settings/viewoptions/formsdesign/) { get; set; } | 指定文档是否处于表单设计模式。 |
| [ViewType](../../aspose.words.settings/viewoptions/viewtype/) { get; set; } | 控制 Microsoft Word 中的查看模式。 |
| [ZoomPercent](../../aspose.words.settings/viewoptions/zoompercent/) { get; set; } | 获取或设置要查看文档的百分比（10 到 500 之间）。 |
| [ZoomType](../../aspose.words.settings/viewoptions/zoomtype/) { get; set; } | 获取或设置基于窗口大小的缩放值。 |

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

显示如何设置自定义缩放类型，旧版本的 Microsoft Word 将在加载时应用于文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// 将“ZoomType”属性设置为“ZoomType.PageWidth”以获取 Microsoft Word
// 自动缩放文档以适应页面的宽度。
// 将“ZoomType”属性设置为“ZoomType.FullPage”以获取 Microsoft Word
// 自动缩放文档以使整个第一页可见。
// 将“ZoomType”属性设置为“ZoomType.TextFit”以获取 Microsoft Word
// 自动缩放文档以适应第一页的内部文本边距。
doc.ViewOptions.ZoomType = zoomType;

doc.Save(ArtifactsDir + "ViewOptions.SetZoomType.doc");
```

### 也可以看看

* class [Document](../../aspose.words/document/)
* property [ViewOptions](../../aspose.words/document/viewoptions/)
* 命名空间 [Aspose.Words.Settings](../../aspose.words.settings/)
* 部件 [Aspose.Words](../../)


