---
title: FieldSet.BookmarkText
second_title: Aspose.Words for .NET API 参考
description: FieldSet 财产. 获取或设置书签的新文本
type: docs
weight: 30
url: /zh/net/aspose.words.fields/fieldset/bookmarktext/
---
## FieldSet.BookmarkText property

获取或设置书签的新文本。

```csharp
public string BookmarkText { get; set; }
```

### 例子

演示如何使用 SET 字段创建带有书签的文本，然后使用 REF 字段将其显示在文档中。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

 // 使用 SET 字段命名书签文本。
// 这个字段引用的“书签”不是出现在文本中的书签结构，而是一个命名变量。
FieldSet fieldSet = (FieldSet)builder.InsertField(FieldType.FieldSet, false);
fieldSet.BookmarkName = "MyBookmark";
fieldSet.BookmarkText = "Hello world!";
fieldSet.Update();

Assert.AreEqual(" SET  MyBookmark \"Hello world!\"", fieldSet.GetFieldCode());

// 在 REF 字段中按名称引用书签并显示其内容。
FieldRef fieldRef = (FieldRef)builder.InsertField(FieldType.FieldRef, true);
fieldRef.BookmarkName = "MyBookmark";
fieldRef.Update();

Assert.AreEqual(" REF  MyBookmark", fieldRef.GetFieldCode());
Assert.AreEqual("Hello world!", fieldRef.Result);

doc.Save(ArtifactsDir + "Field.SET.REF.docx");
```

### 也可以看看

* class [FieldSet](../)
* 命名空间 [Aspose.Words.Fields](../../fieldset/)
* 部件 [Aspose.Words](../../../)


