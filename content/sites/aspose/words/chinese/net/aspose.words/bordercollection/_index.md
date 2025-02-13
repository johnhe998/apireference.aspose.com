---
title: Class BorderCollection
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.BorderCollection 班级. 边框对象的集合
type: docs
weight: 80
url: /zh/net/aspose.words/bordercollection/
---
## BorderCollection class

边框对象的集合。

```csharp
public sealed class BorderCollection : IEnumerable<Border>
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Bottom](../../aspose.words/bordercollection/bottom/) { get; } | 获取底部边框。 |
| [Color](../../aspose.words/bordercollection/color/) { get; set; } | 获取或设置边框颜色。 |
| [Count](../../aspose.words/bordercollection/count/) { get; } | 获取集合中的边框数。 |
| [DistanceFromText](../../aspose.words/bordercollection/distancefromtext/) { get; set; } | 获取或设置边框与文本的距离，以点为单位。 |
| [Horizontal](../../aspose.words/bordercollection/horizontal/) { get; } | 获取单元格或符合段落之间使用的水平边框。 |
| [Item](../../aspose.words/bordercollection/item/) { get; } | 按边框类型检索边框对象。 (2 indexers) |
| [Left](../../aspose.words/bordercollection/left/) { get; } | 获取左边框。 |
| [LineStyle](../../aspose.words/bordercollection/linestyle/) { get; set; } | 获取或设置边框样式 |
| [LineWidth](../../aspose.words/bordercollection/linewidth/) { get; set; } | 获取或设置以点为单位的边框宽度。 |
| [Right](../../aspose.words/bordercollection/right/) { get; } | 获取右边框。 |
| [Shadow](../../aspose.words/bordercollection/shadow/) { get; set; } | 获取或设置边框是否有阴影的值。 |
| [Top](../../aspose.words/bordercollection/top/) { get; } | 获取上边框。 |
| [Vertical](../../aspose.words/bordercollection/vertical/) { get; } | 获取单元格之间使用的垂直边框。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [ClearFormatting](../../aspose.words/bordercollection/clearformatting/)() | 删除对象的所有边框。 |
| [Equals](../../aspose.words/bordercollection/equals/#equals)(BorderCollection) | 比较边框的集合。 |
| [GetEnumerator](../../aspose.words/bordercollection/getenumerator/)() | 返回一个可用于遍历集合中所有边框的枚举器对象。 |

### 评论

不同的文档元素有不同的边框。 例如，ParagraphFormat 有下、左、右和上边框。 可以为每个边框单独指定不同的格式或 枚举所有边框并应用相同的格式。

### 例子

演示如何插入带有上边框的段落。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Border topBorder = builder.ParagraphFormat.Borders[BorderType.Top];
topBorder.Color = Color.Red;
topBorder.LineWidth = 4.0d;
topBorder.LineStyle = LineStyle.DashSmallGap;

builder.Writeln("Text with a red top border.");

doc.Save(ArtifactsDir + "Border.ParagraphTopBorder.docx");
```

### 也可以看看

* class [Border](../border/)
* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


