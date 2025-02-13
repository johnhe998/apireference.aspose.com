---
title: Class TxtSaveOptions
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Saving.TxtSaveOptions 班级. 可用于在将文档保存到Text格式.
type: docs
weight: 5380
url: /zh/net/aspose.words.saving/txtsaveoptions/
---
## TxtSaveOptions class

可用于在将文档保存到Text格式.

```csharp
public class TxtSaveOptions : TxtSaveOptionsBase
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [TxtSaveOptions](txtsaveoptions/)() | 默认构造函数。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [AddBidiMarks](../../aspose.words.saving/txtsaveoptions/addbidimarks/) { get; set; } | 指定以纯文本格式导出时是否在每次 BiDi 运行之前添加双向标记。 |
| [AllowEmbeddingPostScriptFonts](../../aspose.words.saving/saveoptions/allowembeddingpostscriptfonts/) { get; set; } | 获取或设置一个布尔值，该值指示是否允许在保存文档中嵌入 TrueType 字体时使用 PostScript 轮廓嵌入字体 。 默认值为 **错误的**. |
| [CustomTimeZoneInfo](../../aspose.words.saving/saveoptions/customtimezoneinfo/) { get; set; } | 获取或设置用于日期/时间字段的自定义本地时区。 |
| [DefaultTemplate](../../aspose.words.saving/saveoptions/defaulttemplate/) { get; set; } | 获取或设置默认模板的路径（包括文件名）。 此属性的默认值为 **空字符串**(Empty ). |
| [Dml3DEffectsRenderingMode](../../aspose.words.saving/saveoptions/dml3deffectsrenderingmode/) { get; set; } | 获取或设置一个值，确定如何渲染 3D 效果。 |
| virtual [DmlEffectsRenderingMode](../../aspose.words.saving/saveoptions/dmleffectsrenderingmode/) { get; set; } | 获取或设置一个值，确定如何呈现 DrawingML 效果。 |
| [DmlRenderingMode](../../aspose.words.saving/saveoptions/dmlrenderingmode/) { get; set; } | 获取或设置一个值，确定如何呈现 DrawingML 形状。 |
| [Encoding](../../aspose.words.saving/txtsaveoptionsbase/encoding/) { get; set; } | 指定以文本格式导出时要使用的编码。 默认值为 **编码.UTF8**. |
| [ExportGeneratorName](../../aspose.words.saving/saveoptions/exportgeneratorname/) { get; set; } | 如果为真，则将 Aspose.Words 的名称和版本嵌入到生成的文件中。 默认值为 **真的**. |
| [ExportHeadersFootersMode](../../aspose.words.saving/txtsaveoptionsbase/exportheadersfootersmode/) { get; set; } | 指定页眉和页脚导出为文本格式的方式。 默认值为PrimaryOnly. |
| [FlatOpcXmlMappingOnly](../../aspose.words.saving/saveoptions/flatopcxmlmappingonly/) { get; set; } | 获取或设置值，确定允许映射哪些文档格式[`XmlMapping`](../../aspose.words.markup/structureddocumenttag/xmlmapping/). 仅默认FlatOpc允许映射文档格式。 |
| [ForcePageBreaks](../../aspose.words.saving/txtsaveoptionsbase/forcepagebreaks/) { get; set; } | 允许指定在导出期间是否应保留分页符。 |
| [ImlRenderingMode](../../aspose.words.saving/saveoptions/imlrenderingmode/) { get; set; } | 获取或设置一个值，确定如何呈现墨水 (InkML) 对象。 |
| [ListIndentation](../../aspose.words.saving/txtsaveoptions/listindentation/) { get; } | 获取一个 ListIndentation 对象，该对象指定用于列表级别的缩进的字符数和字符数。 默认情况下，它是字符 '\0' 的零计数，这意味着没有缩进。 |
| [MaxCharactersPerLine](../../aspose.words.saving/txtsaveoptions/maxcharactersperline/) { get; set; } | 获取或设置一个整数值，指定每行的最大字符数。 默认值为0，即无限制。 |
| [MemoryOptimization](../../aspose.words.saving/saveoptions/memoryoptimization/) { get; set; } | 获取或设置值确定是否应在保存文档之前执行内存优化。 此属性的默认值为 **错误的**. |
| [ParagraphBreak](../../aspose.words.saving/txtsaveoptionsbase/paragraphbreak/) { get; set; } | 指定以文本格式导出时用作分节符的字符串。 |
| [PreserveTableLayout](../../aspose.words.saving/txtsaveoptions/preservetablelayout/) { get; set; } | 指定程序在以纯文本格式保存时是否应尝试保留表格布局。 默认值为 **错误的**. |
| [PrettyFormat](../../aspose.words.saving/saveoptions/prettyformat/) { get; set; } | 什么时候`真的` , 在适用的情况下输出漂亮的格式。 默认值为 **错误的**. |
| [ProgressCallback](../../aspose.words.saving/saveoptions/progresscallback/) { get; set; } | 在保存文档期间调用并接受有关保存进度的数据。 |
| override [SaveFormat](../../aspose.words.saving/txtsaveoptions/saveformat/) { get; set; } | 指定使用此保存选项对象时文档将保存的格式。 只能是Text. |
| [SimplifyListLabels](../../aspose.words.saving/txtsaveoptions/simplifylistlabels/) { get; set; } | 指定程序是否应简化列表标签，以防 复杂标签格式不能由纯文本充分表示。 |
| [TempFolder](../../aspose.words.saving/saveoptions/tempfolder/) { get; set; } | 指定保存到 DOC 或 DOCX 文件时使用的临时文件的文件夹。 默认情况下，此属性为`无效的`并且没有使用临时文件。 |
| [UpdateCreatedTimeProperty](../../aspose.words.saving/saveoptions/updatecreatedtimeproperty/) { get; set; } | 获取或设置一个值，确定是否[`CreatedTime`](../../aspose.words.properties/builtindocumentproperties/createdtime/)属性在保存前更新。 默认值为 false； |
| [UpdateFields](../../aspose.words.saving/saveoptions/updatefields/) { get; set; } | 获取或设置一个值，该值确定在将文档保存为固定页面格式之前是否应更新某些类型的字段。 此属性的默认值为 **真的**. |
| [UpdateLastPrintedProperty](../../aspose.words.saving/saveoptions/updatelastprintedproperty/) { get; set; } | 获取或设置一个值，确定是否[`LastPrinted`](../../aspose.words.properties/builtindocumentproperties/lastprinted/)属性在保存之前更新。 |
| [UpdateLastSavedTimeProperty](../../aspose.words.saving/saveoptions/updatelastsavedtimeproperty/) { get; set; } | 获取或设置一个值，确定是否[`LastSavedTime`](../../aspose.words.properties/builtindocumentproperties/lastsavedtime/)属性在保存之前更新。 |
| [UpdateSdtContent](../../aspose.words.saving/saveoptions/updatesdtcontent/) { get; set; } | 获取或设置值确定内容是否[`StructuredDocumentTag`](../../aspose.words.markup/structureddocumenttag/)在保存之前更新。 |
| [UseAntiAliasing](../../aspose.words.saving/saveoptions/useantialiasing/) { get; set; } | 获取或设置一个值，确定是否使用抗锯齿进行渲染。 |
| [UseHighQualityRendering](../../aspose.words.saving/saveoptions/usehighqualityrendering/) { get; set; } | 获取或设置一个确定是否使用高质量（即慢速）渲染算法的值。 |

### 例子

显示如何使用自定义分节符保存 .txt 文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Paragraph 1.");
builder.Writeln("Paragraph 2.");
builder.Write("Paragraph 3.");

// 创建一个“TxtSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改我们如何将文档保存为纯文本。
TxtSaveOptions txtSaveOptions = new TxtSaveOptions();

Assert.AreEqual(SaveFormat.Text, txtSaveOptions.SaveFormat);

// 将“ParagraphBreak”设置为我们希望放在每个段落末尾的自定义值。
txtSaveOptions.ParagraphBreak = " End of paragraph.\n\n\t";

doc.Save(ArtifactsDir + "TxtSaveOptions.ParagraphBreak.txt", txtSaveOptions);

string docText = File.ReadAllText(ArtifactsDir + "TxtSaveOptions.ParagraphBreak.txt");

Assert.AreEqual("Paragraph 1. End of paragraph.\n\n\t" +
                "Paragraph 2. End of paragraph.\n\n\t" +
                "Paragraph 3. End of paragraph.\n\n\t", docText);
```

### 也可以看看

* class [TxtSaveOptionsBase](../txtsaveoptionsbase/)
* 命名空间 [Aspose.Words.Saving](../../aspose.words.saving/)
* 部件 [Aspose.Words](../../)


