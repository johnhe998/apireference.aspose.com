---
title: FieldCollection.Clear
second_title: Aspose.Words for .NET API 参考
description: FieldCollection 方法. 从文档和此集合本身中删除此集合的所有字段
type: docs
weight: 30
url: /zh/net/aspose.words.fields/fieldcollection/clear/
---
## FieldCollection.Clear method

从文档和此集合本身中删除此集合的所有字段。

```csharp
public void Clear()
```

### 例子

显示如何从字段集合中删除字段。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" DATE \\@ \"dddd, d MMMM yyyy\" ");
builder.InsertField(" TIME ");
builder.InsertField(" REVNUM ");
builder.InsertField(" AUTHOR  \"John Doe\" ");
builder.InsertField(" SUBJECT \"My Subject\" ");
builder.InsertField(" QUOTE \"Hello world!\" ");
doc.UpdateFields();

FieldCollection fields = doc.Range.Fields;

Assert.AreEqual(6, fields.Count);

// 下面是从字段集合中删除字段的四种方法。
// 1 - 获取一个字段来移除自身：
fields[0].Remove();
Assert.AreEqual(5, fields.Count);

// 2 - 获取集合以删除我们传递给其删除方法的字段：
Field lastField = fields[3];
fields.Remove(lastField);
Assert.AreEqual(4, fields.Count);

// 3 - 从集合中的索引处删除一个字段：
fields.RemoveAt(2);
Assert.AreEqual(3, fields.Count);

// 4 - 一次从集合中删除所有字段：
fields.Clear();
Assert.AreEqual(0, fields.Count);
```

### 也可以看看

* class [FieldCollection](../)
* 命名空间 [Aspose.Words.Fields](../../fieldcollection/)
* 部件 [Aspose.Words](../../../)


