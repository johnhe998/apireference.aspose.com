---
title: Enum DmlEffectsRenderingMode
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Saving.DmlEffectsRenderingMode 枚举. 指定如何将 DrawingML 效果呈现为固定页面格式
type: docs
weight: 4650
url: /zh/net/aspose.words.saving/dmleffectsrenderingmode/
---
## DmlEffectsRenderingMode enumeration

指定如何将 DrawingML 效果呈现为固定页面格式。

```csharp
public enum DmlEffectsRenderingMode
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Simplified | `0` | DrawingML 效果的渲染被简化。 |
| None | `1` | 不渲染 DrawingML 效果。 |
| Fine | `2` | DrawingML 效果以精细模式呈现，涉及高级处理。 在这种模式下，效果呈现效果更好，但性能成本高于Simplified模式. |

### 例子

展示了当我们将文档保存为 PDF 时如何在文档中配置 DrawingML 效果的渲染质量。

```csharp
Document doc = new Document(MyDir + "DrawingML shape effects.docx");

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
PdfSaveOptions options = new PdfSaveOptions();

// 将“DmlEffectsRenderingMode”属性设置为“DmlEffectsRenderingMode.None”以丢弃所有 DrawingML 效果。
// 将“DmlEffectsRenderingMode”属性设置为“DmlEffectsRenderingMode.Simplified”
// 渲染一个简化版的 DrawingML 效果。
// 将“DmlEffectsRenderingMode”属性设置为“DmlEffectsRenderingMode.Fine”以
// 以更高的准确性和更高的处理成本渲染 DrawingML 效果。
options.DmlEffectsRenderingMode = effectsRenderingMode;

Assert.AreEqual(DmlRenderingMode.DrawingML, options.DmlRenderingMode);

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLEffects.pdf", options);
```

### 也可以看看

* 命名空间 [Aspose.Words.Saving](../../aspose.words.saving/)
* 部件 [Aspose.Words](../../)


