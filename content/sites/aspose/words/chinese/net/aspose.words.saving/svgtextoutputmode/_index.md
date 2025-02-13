---
title: Enum SvgTextOutputMode
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Saving.SvgTextOutputMode 枚举. 
type: docs
weight: 5330
url: /zh/net/aspose.words.saving/svgtextoutputmode/
---
## SvgTextOutputMode enumeration

```csharp
public enum SvgTextOutputMode
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| UseSvgFonts | `0` | SVG 字体用于渲染文本。请注意，并非所有浏览器都支持 SVG 字体。 |
| UseTargetMachineFonts | `1` | 安装在目标机器上的字体用于渲染文本。 注意，如果文档中使用的某些字体在目标机器上不可用，文档的外观可能会有所不同。 |
| UsePlacedGlyphs | `2` | 使用曲线渲染文本。请注意，如果您使用此选项，文本选择将不起作用。 |

### 例子

演示如何在将 .docx 文档转换为 .svg 时模拟图像的属性。

```csharp
Document doc = new Document(MyDir + "Document.docx");

// 将 SvgSaveOptions 对象配置为没有页面边框或可选文本的保存。
SvgSaveOptions options = new SvgSaveOptions
{
    FitToViewPort = true,
    ShowPageBorder = false,
    TextOutputMode = SvgTextOutputMode.UsePlacedGlyphs
};

doc.Save(ArtifactsDir + "SvgSaveOptions.SaveLikeImage.svg", options);
```

### 也可以看看

* 命名空间 [Aspose.Words.Saving](../../aspose.words.saving/)
* 部件 [Aspose.Words](../../)


