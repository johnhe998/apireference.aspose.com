---
title: BuiltInDocumentProperties.Category
second_title: Aspose.Words for .NET API 参考
description: BuiltInDocumentProperties 财产. 获取或设置文档的类别
type: docs
weight: 30
url: /zh/net/aspose.words.properties/builtindocumentproperties/category/
---
## BuiltInDocumentProperties.Category property

获取或设置文档的类别。

```csharp
public string Category { get; set; }
```

### 例子

显示如何使用“描述”类别中的内置文档属性。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;

// 下面是四个内置的文档属性，它们具有可以在文档正文中显示其值的字段。
// 1 - “作者”属性，我们可以使用 AUTHOR 字段显示：
properties.Author = "John Doe";
builder.Write("Author:\t");
builder.InsertField(FieldType.FieldAuthor, true);

// 2 - “Title”属性，我们可以使用 TITLE 字段显示：
properties.Title = "John's Document";
builder.Write("\nDoc title:\t");
builder.InsertField(FieldType.FieldTitle, true);

// 3 - “主题”属性，我们可以使用 SUBJECT 字段显示：
properties.Subject = "My subject";
builder.Write("\nSubject:\t");
builder.InsertField(FieldType.FieldSubject, true);

// 4 - “Comments”属性，我们可以使用 COMMENTS 字段显示：
properties.Comments = $"This is {properties.Author}'s document about {properties.Subject}";
builder.Write("\nComments:\t\"");
builder.InsertField(FieldType.FieldComments, true);
builder.Write("\"");

// “类别”内置属性没有可以显示其值的字段。
properties.Category = "My category";

// 我们可以通过用分号分隔“Keywords”属性的字符串值来为一个文档设置多个关键字。
properties.Keywords = "Tag 1; Tag 2; Tag 3";

// 我们可以在Windows资源管理器中右键点击这个文档，在“属性”->中找到这些属性“细节”。
// “Author”内置属性在“Origin”组，其他在“Description”组。
doc.Save(ArtifactsDir + "DocumentProperties.Description.docx");
```

### 也可以看看

* class [BuiltInDocumentProperties](../)
* 命名空间 [Aspose.Words.Properties](../../builtindocumentproperties/)
* 部件 [Aspose.Words](../../../)


