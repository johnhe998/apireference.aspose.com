---
title: FieldMergingArgsBase.DocumentFieldName
second_title: Aspose.Words for .NET API 参考
description: FieldMergingArgsBase 财产. 获取文档中指定的合并字段的名称
type: docs
weight: 20
url: /zh/net/aspose.words.mailmerging/fieldmergingargsbase/documentfieldname/
---
## FieldMergingArgsBase.DocumentFieldName property

获取文档中指定的合并字段的名称。

```csharp
public string DocumentFieldName { get; }
```

### 评论

如果您有从文档字段名称到不同数据源字段名称的映射， ，那么这是文档中指定的原始字段名称。

如果您指定了字段名称前缀，例如文档中的“Image:MyFieldName”， 那么 **文档字段名**返回不带前缀的字段名称，即“MyFieldName”。

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

* class [FieldMergingArgsBase](../)
* 命名空间 [Aspose.Words.MailMerging](../../fieldmergingargsbase/)
* 部件 [Aspose.Words](../../../)


