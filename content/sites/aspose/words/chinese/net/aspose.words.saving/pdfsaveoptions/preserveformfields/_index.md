---
title: PdfSaveOptions.PreserveFormFields
second_title: Aspose.Words for .NET API 参考
description: PdfSaveOptions 财产. 指定是否将 Microsoft Word 表单域保留为 PDF 中的表单域或将其转换为文本 默认为错误的.
type: docs
weight: 240
url: /zh/net/aspose.words.saving/pdfsaveoptions/preserveformfields/
---
## PdfSaveOptions.PreserveFormFields property

指定是否将 Microsoft Word 表单域保留为 PDF 中的表单域或将其转换为文本。 默认为`错误的`.

```csharp
public bool PreserveFormFields { get; set; }
```

### 评论

Microsoft Word 表单域包括文本输入、下拉和复选框控件。

当设置为`错误的` ，这些字段将作为文本导出为 PDF。当设置为`真的`, 这些字段将导出为 PDF 表单字段。

将表单域作为表单域导出为 PDF 时，可能会出现一些格式丢失，因为 PDF form fields 不支持 Microsoft Word 表单域的所有功能。

此外，输出大小取决于内容大小，因为 Microsoft Word 中的可编辑表单是 内联对象。

PDF/A 合规性禁止可编辑表单。`错误的`保存到 PDF/A 时将自动使用值 。

保存为 PDF/UA 时不支持表单域。`错误的`值将被自动使用。

### 例子

演示如何使用 Save 方法和 PdfSaveOptions 类将文档保存为 PDF 格式。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please select a fruit: ");

// 插入一个组合框，允许用户从字符串集合中选择一个选项。
builder.InsertComboBox("MyComboBox", new[] { "Apple", "Banana", "Cherry" }, 0);

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
PdfSaveOptions pdfOptions = new PdfSaveOptions();

// 将“PreserveFormFields”属性设置为“true”以将表单字段保存为输出 PDF 中的交互式对象。
// 将“PreserveFormFields”属性设置为“false”以冻结文档中的所有表单域
// 它们的当前值并将它们显示为输出 PDF 中的纯文本。
pdfOptions.PreserveFormFields = preserveFormFields;

doc.Save(ArtifactsDir + "PdfSaveOptions.PreserveFormFields.pdf", pdfOptions);
```

### 也可以看看

* class [PdfSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../pdfsaveoptions/)
* 部件 [Aspose.Words](../../../)


