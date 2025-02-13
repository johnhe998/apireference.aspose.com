---
title: DocumentBuilder.MoveToField
second_title: Aspose.Words for .NET API 参考
description: DocumentBuilder 方法. 将光标移动到文档中的某个字段
type: docs
weight: 510
url: /zh/net/aspose.words/documentbuilder/movetofield/
---
## DocumentBuilder.MoveToField method

将光标移动到文档中的某个字段。

```csharp
public void MoveToField(Field field, bool isAfter)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| field | Field | 要将光标移动到的字段。 |
| isAfter | Boolean | 如果为 true，则将光标移动到字段结束之后。 如果为 false，将光标移动到字段开始之前。 |

### 例子

显示如何将文档构建器的节点插入点光标移动到特定字段。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 使用 DocumentBuilder 插入一个字段并在其后添加一段文本。
Field field = builder.InsertField(" AUTHOR \"John Doe\" ");

// 构建器的光标当前位于文档的末尾。
Assert.Null(builder.CurrentNode);

// 将光标移动到字段，同时指定将光标放在字段之前还是之后。
builder.MoveToField(field, moveCursorToAfterTheField);

// 请注意，在这两种情况下，光标都位于字段之外。
// 这意味着我们不能像这样使用构建器来编辑字段。
// 要编辑字段，我们可以在字段的 FieldStart 上使用构建器的 MoveTo 方法
// 或 FieldSeparator 节点将光标放在里面。
if (moveCursorToAfterTheField)
{
    Assert.Null(builder.CurrentNode);
    builder.Write(" Text immediately after the field.");

    Assert.AreEqual("\u0013 AUTHOR \"John Doe\" \u0014John Doe\u0015 Text immediately after the field.", 
        doc.GetText().Trim());
}
else
{
    Assert.AreEqual(field.Start, builder.CurrentNode);
    builder.Write("Text immediately before the field. ");

    Assert.AreEqual("Text immediately before the field. \u0013 AUTHOR \"John Doe\" \u0014John Doe\u0015", 
        doc.GetText().Trim());
}
```

### 也可以看看

* class [Field](../../../aspose.words.fields/field/)
* class [DocumentBuilder](../)
* 命名空间 [Aspose.Words](../../documentbuilder/)
* 部件 [Aspose.Words](../../../)


