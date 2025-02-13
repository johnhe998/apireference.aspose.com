---
title: DocumentBuilder.StartColumnBookmark
second_title: Aspose.Words for .NET API 参考
description: DocumentBuilder 方法. 将文档中的当前位置标记为列书签开始该位置必须在表格单元格中
type: docs
weight: 590
url: /zh/net/aspose.words/documentbuilder/startcolumnbookmark/
---
## DocumentBuilder.StartColumnBookmark method

将文档中的当前位置标记为列书签开始。该位置必须在表格单元格中。

```csharp
public BookmarkStart StartColumnBookmark(string bookmarkName)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| bookmarkName | String | 书签的名称。 |

### 返回值

刚刚创建的书签开始节点。

### 评论

列书签涵盖一系列行中的一个或多个列。要创建有效的书签 you 需要同时调用`StartColumnBookmark`和[`EndColumnBookmark`](../endcolumnbookmark/)与相同  **书签名称**范围。

保存文档时将忽略格式错误的书签或具有重复名称的书签。

插入的实际位置[`BookmarkStart`](../../bookmarkstart/)节点可能与当前的 document builder 位置不同。

### 例子

显示如何创建列书签。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartTable();

builder.InsertCell();
// 单元格 1,2,4,5 将被添加书签。
builder.StartColumnBookmark("MyBookmark_1");
// 保存文档时将忽略格式错误的书签或具有重复名称的书签。
builder.StartColumnBookmark("MyBookmark_1");
builder.StartColumnBookmark("BadStartBookmark");
builder.Write("Cell 1");

builder.InsertCell();
builder.Write("Cell 2");

builder.InsertCell();
builder.Write("Cell 3");

builder.EndRow();

builder.InsertCell();
builder.Write("Cell 4");

builder.InsertCell();
builder.Write("Cell 5");
builder.EndColumnBookmark("MyBookmark_1");
builder.EndColumnBookmark("MyBookmark_1");

builder.InsertCell();
builder.Write("Cell 6");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "Bookmarks.CreateColumnBookmark.docx");
```

### 也可以看看

* class [BookmarkStart](../../bookmarkstart/)
* class [DocumentBuilder](../)
* 命名空间 [Aspose.Words](../../documentbuilder/)
* 部件 [Aspose.Words](../../../)


