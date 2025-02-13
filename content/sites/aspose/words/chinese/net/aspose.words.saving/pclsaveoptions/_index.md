---
title: Class PclSaveOptions
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Saving.PclSaveOptions 班级. 可用于在将文档保存到Pcl格式.
type: docs
weight: 5120
url: /zh/net/aspose.words.saving/pclsaveoptions/
---
## PclSaveOptions class

可用于在将文档保存到Pcl格式.

```csharp
public class PclSaveOptions : FixedPageSaveOptions
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [PclSaveOptions](pclsaveoptions/)() | 默认构造函数。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [AllowEmbeddingPostScriptFonts](../../aspose.words.saving/saveoptions/allowembeddingpostscriptfonts/) { get; set; } | 获取或设置一个布尔值，该值指示是否允许在保存文档中嵌入 TrueType 字体时使用 PostScript 轮廓嵌入字体 。 默认值为 **错误的**. |
| [ColorMode](../../aspose.words.saving/fixedpagesaveoptions/colormode/) { get; set; } | 获取或设置一个值，确定如何呈现颜色。 |
| [CustomTimeZoneInfo](../../aspose.words.saving/saveoptions/customtimezoneinfo/) { get; set; } | 获取或设置用于日期/时间字段的自定义本地时区。 |
| [DefaultTemplate](../../aspose.words.saving/saveoptions/defaulttemplate/) { get; set; } | 获取或设置默认模板的路径（包括文件名）。 此属性的默认值为 **空字符串**(Empty ). |
| [Dml3DEffectsRenderingMode](../../aspose.words.saving/saveoptions/dml3deffectsrenderingmode/) { get; set; } | 获取或设置一个值，确定如何渲染 3D 效果。 |
| virtual [DmlEffectsRenderingMode](../../aspose.words.saving/saveoptions/dmleffectsrenderingmode/) { get; set; } | 获取或设置一个值，确定如何呈现 DrawingML 效果。 |
| [DmlRenderingMode](../../aspose.words.saving/saveoptions/dmlrenderingmode/) { get; set; } | 获取或设置一个值，确定如何呈现 DrawingML 形状。 |
| [ExportGeneratorName](../../aspose.words.saving/saveoptions/exportgeneratorname/) { get; set; } | 如果为真，则将 Aspose.Words 的名称和版本嵌入到生成的文件中。 默认值为 **真的**. |
| [FallbackFontName](../../aspose.words.saving/pclsaveoptions/fallbackfontname/) { get; set; } | 将使用的字体名称 如果在打印机和内置字体集合中找不到预期的字体。 |
| [FlatOpcXmlMappingOnly](../../aspose.words.saving/saveoptions/flatopcxmlmappingonly/) { get; set; } | 获取或设置值，确定允许映射哪些文档格式[`XmlMapping`](../../aspose.words.markup/structureddocumenttag/xmlmapping/). 仅默认FlatOpc允许映射文档格式。 |
| [ImlRenderingMode](../../aspose.words.saving/saveoptions/imlrenderingmode/) { get; set; } | 获取或设置一个值，确定如何呈现墨水 (InkML) 对象。 |
| [JpegQuality](../../aspose.words.saving/fixedpagesaveoptions/jpegquality/) { get; set; } | 获取或设置一个值，确定 Html 文档中 JPEG 图像的质量。 |
| [MemoryOptimization](../../aspose.words.saving/saveoptions/memoryoptimization/) { get; set; } | 获取或设置值确定是否应在保存文档之前执行内存优化。 此属性的默认值为 **错误的**. |
| [MetafileRenderingOptions](../../aspose.words.saving/fixedpagesaveoptions/metafilerenderingoptions/) { get; set; } | 允许指定元文件渲染选项。 |
| [NumeralFormat](../../aspose.words.saving/fixedpagesaveoptions/numeralformat/) { get; set; } | 获取或设置[`NumeralFormat`](../numeralformat/)用于渲染数字。 默认使用欧洲数字。 |
| virtual [OptimizeOutput](../../aspose.words.saving/fixedpagesaveoptions/optimizeoutput/) { get; set; } | 标志表示是否需要优化输出。 如果设置了这个标志，多余的嵌套画布和空的画布被删除， 也会连接具有相同格式的相邻字形。 注意：内容显示的准确性可能会受到影响，如果此属性设置为 true。 默认为 false。 |
| [PageSavingCallback](../../aspose.words.saving/fixedpagesaveoptions/pagesavingcallback/) { get; set; } | 允许控制在将文档导出为固定页面格式时如何保存单独的页面。 |
| [PageSet](../../aspose.words.saving/fixedpagesaveoptions/pageset/) { get; set; } | 获取或设置要渲染的页面。 默认为文档中的所有页面。 |
| [PrettyFormat](../../aspose.words.saving/saveoptions/prettyformat/) { get; set; } | 什么时候`真的` , 在适用的情况下输出漂亮的格式。 默认值为 **错误的**. |
| [ProgressCallback](../../aspose.words.saving/saveoptions/progresscallback/) { get; set; } | 在保存文档期间调用并接受有关保存进度的数据。 |
| [RasterizeTransformedElements](../../aspose.words.saving/pclsaveoptions/rasterizetransformedelements/) { get; set; } | 获取或设置一个值，该值确定复杂变换元素 在保存到 PCL 文档之前是否应进行光栅化。 默认为`真的`. |
| override [SaveFormat](../../aspose.words.saving/pclsaveoptions/saveformat/) { get; set; } | 指定使用此保存选项对象时文档将保存的格式。 只能是Pcl. |
| [TempFolder](../../aspose.words.saving/saveoptions/tempfolder/) { get; set; } | 指定保存到 DOC 或 DOCX 文件时使用的临时文件的文件夹。 默认情况下，此属性为`无效的`并且没有使用临时文件。 |
| [UpdateCreatedTimeProperty](../../aspose.words.saving/saveoptions/updatecreatedtimeproperty/) { get; set; } | 获取或设置一个值，确定是否[`CreatedTime`](../../aspose.words.properties/builtindocumentproperties/createdtime/)属性在保存前更新。 默认值为 false； |
| [UpdateFields](../../aspose.words.saving/saveoptions/updatefields/) { get; set; } | 获取或设置一个值，该值确定在将文档保存为固定页面格式之前是否应更新某些类型的字段。 此属性的默认值为 **真的**. |
| [UpdateLastPrintedProperty](../../aspose.words.saving/saveoptions/updatelastprintedproperty/) { get; set; } | 获取或设置一个值，确定是否[`LastPrinted`](../../aspose.words.properties/builtindocumentproperties/lastprinted/)属性在保存之前更新。 |
| [UpdateLastSavedTimeProperty](../../aspose.words.saving/saveoptions/updatelastsavedtimeproperty/) { get; set; } | 获取或设置一个值，确定是否[`LastSavedTime`](../../aspose.words.properties/builtindocumentproperties/lastsavedtime/)属性在保存之前更新。 |
| [UpdateSdtContent](../../aspose.words.saving/saveoptions/updatesdtcontent/) { get; set; } | 获取或设置值确定内容是否[`StructuredDocumentTag`](../../aspose.words.markup/structureddocumenttag/)在保存之前更新。 |
| [UseAntiAliasing](../../aspose.words.saving/saveoptions/useantialiasing/) { get; set; } | 获取或设置一个值，确定是否使用抗锯齿进行渲染。 |
| [UseHighQualityRendering](../../aspose.words.saving/saveoptions/usehighqualityrendering/) { get; set; } | 获取或设置一个确定是否使用高质量（即慢速）渲染算法的值。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [AddPrinterFont](../../aspose.words.saving/pclsaveoptions/addprinterfont/)(string, string) | 添加有关由制造商上传到打印机的字体信息。 |
| override [Equals](../../aspose.words.saving/fixedpagesaveoptions/equals/)(object) | 确定指定对象的值是否与当前对象相等。 |

### 例子

演示如何在将文档保存到 PCL 时栅格化复杂元素。

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

PclSaveOptions saveOptions = new PclSaveOptions
{
    SaveFormat = SaveFormat.Pcl,
    RasterizeTransformedElements = true
};

doc.Save(ArtifactsDir + "PclSaveOptions.RasterizeElements.pcl", saveOptions);
```

### 也可以看看

* class [FixedPageSaveOptions](../fixedpagesaveoptions/)
* 命名空间 [Aspose.Words.Saving](../../aspose.words.saving/)
* 部件 [Aspose.Words](../../)


