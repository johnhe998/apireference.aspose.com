---
title: GradientStopCollection.Insert
second_title: Aspose.Words for .NET API 参考
description: GradientStopCollection 方法. 插入一个GradientStop到指定索引处的集合
type: docs
weight: 50
url: /zh/net/aspose.words.drawing/gradientstopcollection/insert/
---
## GradientStopCollection.Insert method

插入一个[`GradientStop`](../../gradientstop/)到指定索引处的集合。

```csharp
public GradientStop Insert(int index, GradientStop gradientStop)
```

### 例子

显示如何将渐变色标添加到渐变填充。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);
shape.Fill.TwoColorGradient(Color.Green, Color.Red, GradientStyle.Horizontal, GradientVariant.Variant2);

// 获取渐变停止集合。
GradientStopCollection gradientStops = shape.Fill.GradientStops;

// 更改第一个渐变停止点。
gradientStops[0].Color = Color.Aqua;
gradientStops[0].Position = 0.1;
gradientStops[0].Transparency = 0.25;

// 将新的渐变停止添加到集合的末尾。
GradientStop gradientStop = new GradientStop(Color.Brown, 0.5);
gradientStops.Add(gradientStop);

// 删除索引 1 处的渐变停止。
gradientStops.RemoveAt(1);
// 并在同一索引 1 处插入新的渐变停止。
gradientStops.Insert(1, new GradientStop(Color.Chocolate, 0.75, 0.3));

// 删除集合中的最后一个渐变停止点。
gradientStop = gradientStops[2];
gradientStops.Remove(gradientStop);

Assert.AreEqual(2, gradientStops.Count);

Assert.AreEqual(Color.Aqua.ToArgb(), gradientStops[0].Color.ToArgb());
Assert.AreEqual(0.1d, gradientStops[0].Position, 0.01d);
Assert.AreEqual(0.25d, gradientStops[0].Transparency, 0.01d);

Assert.AreEqual(Color.Chocolate.ToArgb(), gradientStops[1].Color.ToArgb());
Assert.AreEqual(0.75d, gradientStops[1].Position, 0.01d);
Assert.AreEqual(0.3d, gradientStops[1].Transparency, 0.01d);

// 使用合规性选项使用 DML 定义形状
// 如果要在文档保存后获取“GradientStops”属性。
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };

doc.Save(ArtifactsDir + "Shape.GradientStops.docx", saveOptions);
```

### 也可以看看

* class [GradientStop](../../gradientstop/)
* class [GradientStopCollection](../)
* 命名空间 [Aspose.Words.Drawing](../../gradientstopcollection/)
* 部件 [Aspose.Words](../../../)


