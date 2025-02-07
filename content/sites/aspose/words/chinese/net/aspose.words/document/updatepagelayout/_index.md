---
title: Document.UpdatePageLayout
second_title: Aspose.Words for .NET API 参考
description: Document 方法. 重建文档的页面布局
type: docs
weight: 750
url: /zh/net/aspose.words/document/updatepagelayout/
---
## Document.UpdatePageLayout method

重建文档的页面布局。

```csharp
public void UpdatePageLayout()
```

### 评论

此方法将文档格式化为页面，并更新文档中的页码相关字段，例如 PAGE、PAGES、PAGEREF 和 REF。将 document 正确呈现为固定页面格式需要最新的页面布局信息。

当您第一次将文档转换为 PDF、XPS、图像或打印时，会自动调用此方法。 但是，如果您在渲染后修改文档然后尝试再次渲染它 - Aspose.Words 不会 自动更新页面布局。在这种情况下，您应该致电`UpdatePageLayout`before 再次渲染。

### 例子

显示何时重新计算文档的页面布局。

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// 将文档保存为 PDF、图像或第一次打印将自动
// 在其页面中缓存文档的布局。
doc.Save(ArtifactsDir + "Document.UpdatePageLayout.1.pdf");

// 以某种方式修改文档。
doc.Styles["Normal"].Font.Size = 6;
doc.Sections[0].PageSetup.Orientation = Aspose.Words.Orientation.Landscape;

 // 在当前版本的 Aspose.Words 中，修改文档不会自动重建
// 缓存的页面布局。如果我们希望缓存布局
// 为了保持最新，我们需要手动更新它。
doc.UpdatePageLayout();

doc.Save(ArtifactsDir + "Document.UpdatePageLayout.2.pdf");
```

### 也可以看看

* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)


