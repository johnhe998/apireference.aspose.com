---
title: Class FieldMergingArgsBase
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.MailMerging.FieldMergingArgsBase 班级. 基类FieldMergingArgs和ImageFieldMergingArgs.
type: docs
weight: 3560
url: /zh/net/aspose.words.mailmerging/fieldmergingargsbase/
---
## FieldMergingArgsBase class

基类[`FieldMergingArgs`](../fieldmergingargs/)和[`ImageFieldMergingArgs`](../imagefieldmergingargs/).

```csharp
public abstract class FieldMergingArgsBase
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Document](../../aspose.words.mailmerging/fieldmergingargsbase/document/) { get; } | 返回[`Document`](./document/)执行邮件合并的对象。 |
| [DocumentFieldName](../../aspose.words.mailmerging/fieldmergingargsbase/documentfieldname/) { get; } | 获取文档中指定的合并字段的名称。 |
| [Field](../../aspose.words.mailmerging/fieldmergingargsbase/field/) { get; } | 获取表示当前合并字段的对象。 |
| [FieldName](../../aspose.words.mailmerging/fieldmergingargsbase/fieldname/) { get; } | 获取数据源中合并字段的名称。 |
| [FieldValue](../../aspose.words.mailmerging/fieldmergingargsbase/fieldvalue/) { get; set; } | 从数据源获取或设置字段的值。 |
| [RecordIndex](../../aspose.words.mailmerging/fieldmergingargsbase/recordindex/) { get; } | 获取正在合并的记录的从零开始的索引。 |
| [TableName](../../aspose.words.mailmerging/fieldmergingargsbase/tablename/) { get; } | 获取当前合并操作的数据表的名称，如果名称不可用，则为空字符串。 |

### 例子

演示如何使用处理 HTML 文档形式的合并数据的自定义回调执行邮件合并。

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(@"MERGEFIELD  html_Title  \b Content");
    builder.InsertField(@"MERGEFIELD  html_Body  \b Content");

    object[] mergeData =
    {
        "<html>" +
            "<h1>" +
                "<span style=\"color: #0000ff; font-family: Arial;\">Hello World!</span>" +
            "</h1>" +
        "</html>", 

        "<html>" +
            "<blockquote>" +
                "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>" +
            "</blockquote>" +
        "</html>"
    };

    doc.MailMerge.FieldMergingCallback = new HandleMergeFieldInsertHtml();
    doc.MailMerge.Execute(new[] { "html_Title", "html_Body" }, mergeData);

    doc.Save(ArtifactsDir + "MailMergeEvent.MergeHtml.docx");
}

/// <summary>
/// 如果邮件合并遇到名称以“html_”前缀开头的MERGEFIELD，
/// 此回调将其合并数据解析为 HTML 内容，并将结果添加到 MERGEFIELD 的文档位置。
/// </summary>
private class HandleMergeFieldInsertHtml : IFieldMergingCallback
{
    /// <summary>
    /// 当邮件合并将数据合并到 MERGEFIELD 时调用。
    /// </summary>
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName.StartsWith("html_") && args.Field.GetFieldCode().Contains("\\b"))
        {
            // 将解析的 HTML 数据添加到文档的正文中。
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);
            builder.InsertHtml((string)args.FieldValue);

            // 因为我们已经手动插入了合并的内容，
             // 我们不需要通过“Text”属性返回内容来响应这个事件。
            args.Text = string.Empty;
        }
    }

    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs args)
    {
        // 没做什么。
    }
}
```

### 也可以看看

* 命名空间 [Aspose.Words.MailMerging](../../aspose.words.mailmerging/)
* 部件 [Aspose.Words](../../)


