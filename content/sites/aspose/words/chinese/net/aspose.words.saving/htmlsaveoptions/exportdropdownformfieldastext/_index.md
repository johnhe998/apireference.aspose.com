---
title: HtmlSaveOptions.ExportDropDownFormFieldAsText
second_title: Aspose.Words for .NET API 参考
description: HtmlSaveOptions 财产. 控制下拉表单字段如何保存为 HTML 或 MHTML 默认值为错误的.
type: docs
weight: 140
url: /zh/net/aspose.words.saving/htmlsaveoptions/exportdropdownformfieldastext/
---
## HtmlSaveOptions.ExportDropDownFormFieldAsText property

控制下拉表单字段如何保存为 HTML 或 MHTML。 默认值为`错误的`.

```csharp
public bool ExportDropDownFormFieldAsText { get; set; }
```

### 评论

当设置为`真的` 将下拉表单字段导出为普通文本。 当`错误的`将下拉表单字段导出为 HTML 中的 SELECT 元素。

导出到 EPUB 时，文本下拉表单字段始终保存为文本，因为 符合此格式的要求。

### 例子

演示如何在保存为 html 时获取下拉组合框表单字段以与段落文本混合。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 使用文档构建器插入一个组合框，其中选择了值“Two”。
builder.InsertComboBox("MyComboBox", new[] { "One", "Two", "Three" }, 1);

// 此 SaveOptions 对象的“ExportDropDownFormFieldAsText”标志允许我们
// 控制将文档保存为 HTML 处理下拉组合框的方式。
// 将其设置为“true”会将每个组合框转换为简单文本
// 显示组合框当前选择的值，有效地冻结它。
// 将其设置为 "false" 将使用 <select> 保留组合框的功能和<选项>标签。
HtmlSaveOptions options = new HtmlSaveOptions();
options.ExportDropDownFormFieldAsText = exportDropDownFormFieldAsText;    

doc.Save(ArtifactsDir + "HtmlSaveOptions.DropDownFormField.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.DropDownFormField.html");

if (exportDropDownFormFieldAsText)
    Assert.True(outDocContents.Contains(
        "<span>Two</span>"));
else
    Assert.True(outDocContents.Contains(
        "<select name=\"MyComboBox\">" +
            "<option>One</option>" +
            "<option selected=\"selected\">Two</option>" +
            "<option>Three</option>" +
        "</select>"));
```

### 也可以看看

* class [HtmlSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../htmlsaveoptions/)
* 部件 [Aspose.Words](../../../)


