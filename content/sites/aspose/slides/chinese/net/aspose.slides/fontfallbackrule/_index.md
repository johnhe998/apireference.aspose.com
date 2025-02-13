---
title: FontFallBackRule
second_title: Aspose.Slides for .NET API 参考
description: 表示字体回退规则
type: docs
weight: 4400
url: /zh/net/aspose.slides/fontfallbackrule/
---
## FontFallBackRule class

表示字体回退规则

```csharp
public class FontFallBackRule : IFontFallBackRule
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [FontFallBackRule](fontfallbackrule#constructor)(uint, uint, string) | 创建新实例。 |
| [FontFallBackRule](fontfallbackrule#constructor_1)(uint, uint, string[]) | 创建新实例。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Count](../../aspose.slides/fontfallbackrule/count) { get; } | 获取实际为范围定义的字体数量。 只读Int32。 |
| [Item](../../aspose.slides/fontfallbackrule/item) { get; } | 获取指定索引处的字体名称。 只读[`IFontFallBackRule`](../ifontfallbackrule)。 |
| [RangeEndIndex](../../aspose.slides/fontfallbackrule/rangeendindex) { get; set; } | 获取连续 unicode 范围的最后一个索引。 |
| [RangeStartIndex](../../aspose.slides/fontfallbackrule/rangestartindex) { get; set; } | 获取连续 unicode 范围的第一个索引。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [AddFallBackFonts](../../aspose.slides/fontfallbackrule/addfallbackfonts#addfallbackfonts)(string) | 将新字体添加到后备字体列表中。 |
| [AddFallBackFonts](../../aspose.slides/fontfallbackrule/addfallbackfonts#addfallbackfonts_1)(string[]) | 将新字体添加到后备字体列表中。 |
| [Clear](../../aspose.slides/fontfallbackrule/clear)() | 从列表中删除所有字体。 |
| [IndexOf](../../aspose.slides/fontfallbackrule/indexof)(string) | 返回集合中指定规则的索引。 |
| [Remove](../../aspose.slides/fontfallbackrule/remove)(string) | 从列表中删除第一次出现的特定 FallBack 字体。 |
| [RemoveAt](../../aspose.slides/fontfallbackrule/removeat)(int) | 删除列表指定索引处的 FallBack 字体。 |
| [ToArray](../../aspose.slides/fontfallbackrule/toarray#toarray)() | 创建并返回一个包含此规则的所有后备字体的数组。 |
| [ToArray](../../aspose.slides/fontfallbackrule/toarray#toarray_1)(int, int) | 创建并返回一个数组，其中包含列表中指定范围内的所有后备字体。 |

### 也可以看看

* interface [IFontFallBackRule](../ifontfallbackrule)
* 命名空间 [Aspose.Slides](../../aspose.slides)
* 部件 [Aspose.Slides](../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Slides.dll -->
