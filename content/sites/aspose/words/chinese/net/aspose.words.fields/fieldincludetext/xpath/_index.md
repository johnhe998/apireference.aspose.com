---
title: FieldIncludeText.XPath
second_title: Aspose.Words for .NET API 参考
description: FieldIncludeText 财产. 获取或设置 XML 文件所需部分的 XPath
type: docs
weight: 90
url: /zh/net/aspose.words.fields/fieldincludetext/xpath/
---
## FieldIncludeText.XPath property

获取或设置 XML 文件所需部分的 XPath。

```csharp
public string XPath { get; set; }
```

### 例子

演示如何创建 INCLUDETEXT 字段并设置其属性。

```csharp
public void FieldIncludeText()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // 下面是两种使用 INCLUDETEXT 字段在本地文件系统中显示 XML 文件内容的方法。
    // 1 - 对 XML 文档执行 XSL 转换：
    FieldIncludeText fieldIncludeText = CreateFieldIncludeText(builder, MyDir + "CD collection data.xml", false, "text/xml", "XML", "ISO-8859-1");
    fieldIncludeText.XslTransformation = MyDir + "CD collection XSL transformation.xsl";

    builder.Writeln();

    // 2 - 使用 XPath 从 XML 文档中获取特定元素：
    fieldIncludeText = CreateFieldIncludeText(builder, MyDir + "CD collection data.xml", false, "text/xml", "XML", "ISO-8859-1");
    fieldIncludeText.NamespaceMappings = "xmlns:n='myNamespace'";
    fieldIncludeText.XPath = "/catalog/cd/title";

    doc.Save(ArtifactsDir + "Field.INCLUDETEXT.docx");

/// <summary>
/// 使用文档构建器插入具有自定义属性的 INCLUDETEXT 字段。
/// </summary>
public FieldIncludeText CreateFieldIncludeText(DocumentBuilder builder, string sourceFullName, bool lockFields, string mimeType, string textConverter, string encoding)
{
    FieldIncludeText fieldIncludeText = (FieldIncludeText)builder.InsertField(FieldType.FieldIncludeText, true);
    fieldIncludeText.SourceFullName = sourceFullName;
    fieldIncludeText.LockFields = lockFields;
    fieldIncludeText.MimeType = mimeType;
    fieldIncludeText.TextConverter = textConverter;
    fieldIncludeText.Encoding = encoding;

    return fieldIncludeText;
}
```

### 也可以看看

* class [FieldIncludeText](../)
* 命名空间 [Aspose.Words.Fields](../../fieldincludetext/)
* 部件 [Aspose.Words](../../../)


