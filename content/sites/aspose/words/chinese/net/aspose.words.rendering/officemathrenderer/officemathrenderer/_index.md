---
title: OfficeMathRenderer.OfficeMathRenderer
second_title: Aspose.Words for .NET API 参考
description: OfficeMathRenderer 构造函数. 初始化这个类的一个新实例
type: docs
weight: 10
url: /zh/net/aspose.words.rendering/officemathrenderer/officemathrenderer/
---
## OfficeMathRenderer constructor

初始化这个类的一个新实例。

```csharp
public OfficeMathRenderer(OfficeMath math)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| math | OfficeMath | 要呈现的 OfficeMath 对象。 |

### 例子

展示如何测量和缩放形状。

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);
OfficeMathRenderer renderer = new OfficeMathRenderer(officeMath);

// 验证 OfficeMath 对象在渲染时将创建的图像的大小。
Assert.AreEqual(119.0f, renderer.SizeInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.SizeInPoints.Height, 0.1f);

Assert.AreEqual(119.0f, renderer.BoundsInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.BoundsInPoints.Height, 0.1f);

// 具有透明部分的形状可能在“OpaqueBoundsInPoints”属性中包含不同的值。
Assert.AreEqual(119.0f, renderer.OpaqueBoundsInPoints.Width, 0.2f);
Assert.AreEqual(14.2f, renderer.OpaqueBoundsInPoints.Height, 0.1f);

// 以像素为单位获取形状大小，线性缩放到特定的 DPI。
Rectangle bounds = renderer.GetBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

// 以像素为单位获取形状大小，但水平和垂直尺寸使用不同的 DPI。
bounds = renderer.GetBoundsInPixels(1.0f, 96.0f, 150.0f);
Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(28, bounds.Height);

// 这里的不透明边界也可能不同。
bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f, 150.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(30, bounds.Height);
```

### 也可以看看

* class [OfficeMath](../../../aspose.words.math/officemath/)
* class [OfficeMathRenderer](../)
* 命名空间 [Aspose.Words.Rendering](../../officemathrenderer/)
* 部件 [Aspose.Words](../../../)


