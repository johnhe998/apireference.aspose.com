---
title: FieldMergingArgsBase.FieldValue
second_title: Aspose.Words for .NET API 参考
description: FieldMergingArgsBase 财产. 从数据源获取或设置字段的值
type: docs
weight: 50
url: /zh/net/aspose.words.mailmerging/fieldmergingargsbase/fieldvalue/
---
## FieldMergingArgsBase.FieldValue property

从数据源获取或设置字段的值。

```csharp
public object FieldValue { get; set; }
```

### 评论

此属性包含邮件合并引擎刚刚从您的数据源 为该字段选择的值。您也可以通过设置属性来替换该值。

### 例子

显示如何编辑 MERGEFIELD 在发生邮件合并时收到的值。

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // 插入一些带有格式开关的 MERGEFIELD，它们将编辑它们在邮件合并期间将收到的值。
    builder.InsertField("MERGEFIELD text_Field1 \\* Caps", null);
    builder.Write(", ");
    builder.InsertField("MERGEFIELD text_Field2 \\* Upper", null);
    builder.Write(", ");
    builder.InsertField("MERGEFIELD numeric_Field1 \\# 0.0", null);

    builder.Document.MailMerge.FieldMergingCallback = new FieldValueMergingCallback();

    builder.Document.MailMerge.Execute(
        new string[] { "text_Field1", "text_Field2", "numeric_Field1" },
        new object[] { "Field 1", "Field 2", 10 });
    string t = doc.GetText().Trim();
    Assert.AreEqual("Merge Value For \"Text_Field1\": Field 1, MERGE VALUE FOR \"TEXT_FIELD2\": FIELD 2, 10000.0", doc.GetText().Trim());
}

/// <summary>
/// 编辑 MERGEFIELD 在邮件合并期间收到的值。
/// MERGEFIELD 的名称必须有一个前缀，此回调才能对其值生效。
/// </summary>
private class FieldValueMergingCallback : IFieldMergingCallback
{
    /// <summary>
    /// 当邮件合并将数据合并到 MERGEFIELD 时调用。
    /// </summary>
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs e)
    {
        if (e.FieldName.StartsWith("text_"))
            e.FieldValue = $"Merge value for \"{e.FieldName}\": {(string)e.FieldValue}";
        else if (e.FieldName.StartsWith("numeric_"))
            e.FieldValue = (int)e.FieldValue * 1000;
    }

    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs e)
    {
        // 没做什么。
    }
}
```

### 也可以看看

* class [FieldMergingArgsBase](../)
* 命名空间 [Aspose.Words.MailMerging](../../fieldmergingargsbase/)
* 部件 [Aspose.Words](../../../)


