---
title: Class TxtLoadOptions
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Loading.TxtLoadOptions 班级. 允许在加载时指定其他选项Text文档成一个Document对象.
type: docs
weight: 3530
url: /zh/net/aspose.words.loading/txtloadoptions/
---
## TxtLoadOptions class

允许在加载时指定其他选项Text文档成一个[`Document`](../../aspose.words/document/)对象.

```csharp
public class TxtLoadOptions : LoadOptions
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [TxtLoadOptions](txtloadoptions/)() | 使用默认值初始化此类的新实例。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [BaseUri](../../aspose.words.loading/loadoptions/baseuri/) { get; set; } | 获取或设置将用于在需要时将在文档中找到的相对 URI 解析为绝对 URI 的字符串。 可以是 null 或空字符串。默认为空。 |
| [ConvertMetafilesToPng](../../aspose.words.loading/loadoptions/convertmetafilestopng/) { get; set; } | 获取或设置是否转换元文件（Wmf或者Emf ) 图像到Png图像格式. |
| [ConvertShapeToOfficeMath](../../aspose.words.loading/loadoptions/convertshapetoofficemath/) { get; set; } | 获取或设置是否将带有 EquationXML 的形状转换为 Office Math 对象。 |
| [DetectNumberingWithWhitespaces](../../aspose.words.loading/txtloadoptions/detectnumberingwithwhitespaces/) { get; set; } | 允许指定从纯文本格式导入文档时如何识别编号列表项。 默认值为 true。 |
| [DocumentDirection](../../aspose.words.loading/txtloadoptions/documentdirection/) { get; set; } | 获取或设置文档方向。 默认值为LeftToRight |
| [Encoding](../../aspose.words.loading/loadoptions/encoding/) { get; set; } | 获取或设置将用于加载 HTML、TXT 或 CHM 文档的编码（如果未在文档中指定编码） 。 可以为空。默认为空。 |
| [FlatOpcXmlMappingOnly](../../aspose.words.loading/loadoptions/flatopcxmlmappingonly/) { get; set; } | 获取或设置值，确定允许映射哪些文档格式[`XmlMapping`](../../aspose.words.markup/structureddocumenttag/xmlmapping/). 仅默认FlatOpc允许映射文档格式。 |
| [FontSettings](../../aspose.words.loading/loadoptions/fontsettings/) { get; set; } | 允许指定文档字体设置。 |
| [LanguagePreferences](../../aspose.words.loading/loadoptions/languagepreferences/) { get; } | 获取加载文档时将使用的语言首选项。 |
| [LeadingSpacesOptions](../../aspose.words.loading/txtloadoptions/leadingspacesoptions/) { get; set; } | 获取或设置前导空格处理的首选选项。 默认值为ConvertToIndent. |
| [LoadFormat](../../aspose.words.loading/loadoptions/loadformat/) { get; set; } | 指定要加载的文档的格式。 默认为Auto. |
| [MswVersion](../../aspose.words.loading/loadoptions/mswversion/) { get; set; } | 允许指定文档加载过程应匹配特定的 MS Word 版本。 默认值为Word2019 |
| [Password](../../aspose.words.loading/loadoptions/password/) { get; set; } | 获取或设置打开加密文档的密码。 可以是空字符串或空字符串。默认为空。 |
| [PreserveIncludePictureField](../../aspose.words.loading/loadoptions/preserveincludepicturefield/) { get; set; } | 获取或设置读取Microsoft Word格式时是否保留INCLUDEPICTURE字段。 默认值为false。 |
| [ProgressCallback](../../aspose.words.loading/loadoptions/progresscallback/) { get; set; } | 在加载文档期间调用并接受有关加载进度的数据。 |
| [ResourceLoadingCallback](../../aspose.words.loading/loadoptions/resourceloadingcallback/) { get; set; } | 允许控制从 HTML、MHTML 导入文档时如何加载外部资源（图像、样式表）。 |
| [TempFolder](../../aspose.words.loading/loadoptions/tempfolder/) { get; set; } | 允许在读取文档时使用临时文件。 默认情况下，此属性为`无效的`并且没有使用临时文件。 |
| [TrailingSpacesOptions](../../aspose.words.loading/txtloadoptions/trailingspacesoptions/) { get; set; } | 获取或设置尾随空格处理的首选选项。 默认值为Trim. |
| [UpdateDirtyFields](../../aspose.words.loading/loadoptions/updatedirtyfields/) { get; set; } | 指定是否使用`肮脏的`属性. |
| [WarningCallback](../../aspose.words.loading/loadoptions/warningcallback/) { get; set; } | 在加载操作期间调用，当检测到可能导致数据或格式保真度丢失的问题时调用。 |

### 也可以看看

* class [LoadOptions](../loadoptions/)
* 命名空间 [Aspose.Words.Loading](../../aspose.words.loading/)
* 部件 [Aspose.Words](../../)


