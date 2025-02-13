---
title: 解析字体名称
linktitle: 解析字体名称
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 转换为 HTML 时解决缺失字体名称的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-htmlsaveoptions/resolve-font-names/
---

在本教程中，我们将引导您通过 C# 源代码使用 Aspose.Words for .NET 解决缺失的字体名称。此功能允许您在将文档转换为 HTML 时自动解析缺失的字体名称。

## 第 1 步：项目设置

首先，在您喜欢的 IDE 中创建一个新的 C# 项目。确保在您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：装入文档

在此步骤中，我们将加载要处理的文档。使用以下代码从指定目录加载文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

此代码创建一个实例`Document`通过从指定目录加载文档。

## 第 3 步：配置 HTML 备份选项

现在我们将配置 HTML 保存选项以解决转换期间丢失的字体名称。使用以下代码：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

此代码创建一个实例`HtmlSaveOptions`并设置`ResolveFontNames`选择权`true`在转换为 HTML 时解决缺少的字体名称。此外，`PrettyFormat`选项设置为`true`获得格式良好的 HTML 代码。

## 第 4 步：将文档转换并保存为 HTML

最后，我们将使用之前配置的 HTML 保存选项将文档转换为 HTML。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

此代码通过自动解析缺少的字体名称将文档转换为 HTML，并将转换后的 HTML 文件保存到指定目录。

### 使用 Aspose.Words for .NET 解析字体名称的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

请务必在`dataDir`多变的。