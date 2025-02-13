---
title: LoadOptions.PreserveIncludePictureField
second_title: Aspose.Words for .NET API 参考
description: LoadOptions 财产. 获取或设置读取Microsoft Word格式时是否保留INCLUDEPICTURE字段 默认值为false
type: docs
weight: 120
url: /zh/net/aspose.words.loading/loadoptions/preserveincludepicturefield/
---
## LoadOptions.PreserveIncludePictureField property

获取或设置读取Microsoft Word格式时是否保留INCLUDEPICTURE字段。 默认值为false。

```csharp
public bool PreserveIncludePictureField { get; set; }
```

### 评论

默认情况下，INCLUDEPICTURE 字段转换为形状对象。如果您需要 要保留的字段，您可以覆盖它，例如，如果您希望以编程方式更新它。但是请注意，this 方法对于 Aspose.Words 并不常见。自行承担使用风险。

一种可能的用例可能是使用 MERGEFIELD 作为子字段来动态更改图片的源 path 。在这种情况下，您需要将 INCLUDEPICTURE 保留在模型中。

### 例子

显示在加载文档时如何保留或丢弃 INCLUDEPICTURE 字段。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldIncludePicture includePicture = (FieldIncludePicture)builder.InsertField(FieldType.FieldIncludePicture, true);
includePicture.SourceFullName = ImageDir + "Transparent background logo.png";
includePicture.Update(true);

using (MemoryStream docStream = new MemoryStream())
{
    doc.Save(docStream, new OoxmlSaveOptions(SaveFormat.Docx));

    // 我们可以在 LoadOptions 对象中设置一个标志来决定是否转换所有的 INCLUDEPICTURE 字段
    // 在加载包含它们的文档时进入图像形状。
    LoadOptions loadOptions = new LoadOptions
    {
        PreserveIncludePictureField = preserveIncludePictureField
    };

    doc = new Document(docStream, loadOptions);

    if (preserveIncludePictureField)
    {
        Assert.True(doc.Range.Fields.Any(f => f.Type == FieldType.FieldIncludePicture));

        doc.UpdateFields();
        doc.Save(ArtifactsDir + "Field.PreserveIncludePicture.docx");
    }
    else
    {
        Assert.False(doc.Range.Fields.Any(f => f.Type == FieldType.FieldIncludePicture));
    }
}
```

### 也可以看看

* class [LoadOptions](../)
* 命名空间 [Aspose.Words.Loading](../../loadoptions/)
* 部件 [Aspose.Words](../../../)


