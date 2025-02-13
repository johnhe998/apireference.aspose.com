---
title: Class FieldCollection
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Fields.FieldCollection 班级. 集合Field表示指定范围内的字段的对象
type: docs
weight: 1540
url: /zh/net/aspose.words.fields/fieldcollection/
---
## FieldCollection class

集合[`Field`](../field/)表示指定范围内的字段的对象。

```csharp
public class FieldCollection : IEnumerable<Field>
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Count](../../aspose.words.fields/fieldcollection/count/) { get; } | 返回集合中的字段数。 |
| [Item](../../aspose.words.fields/fieldcollection/item/) { get; } | 返回指定索引处的字段。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [Clear](../../aspose.words.fields/fieldcollection/clear/)() | 从文档和此集合本身中删除此集合的所有字段。 |
| [GetEnumerator](../../aspose.words.fields/fieldcollection/getenumerator/)() | 返回一个枚举器对象。 |
| [Remove](../../aspose.words.fields/fieldcollection/remove/)(Field) | 从此集合和文档中删除指定字段。 |
| [RemoveAt](../../aspose.words.fields/fieldcollection/removeat/)(int) | 从此集合和文档中删除指定索引处的字段。 |

### 评论

此集合的一个实例迭代开始落在指定范围内的字段。

这`FieldCollection`集合不拥有它包含的字段，而只是字段的选择。

这`FieldCollection`集合是“实时的”，即对创建它的节点 object 的子节点的更改会立即反映在由`FieldCollection` 属性和方法。

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

展示如何使用字段集合。

```csharp
{
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

    // 遍历字段集合，并打印内容和类型
    // 使用自定义访问者实现的每个字段。
    FieldVisitor fieldVisitor = new FieldVisitor();

    using (IEnumerator<Field> fieldEnumerator = fields.GetEnumerator())
    {
        while (fieldEnumerator.MoveNext())
        {
            if (fieldEnumerator.Current != null)
            {
                fieldEnumerator.Current.Start.Accept(fieldVisitor);
                fieldEnumerator.Current.Separator?.Accept(fieldVisitor);
                fieldEnumerator.Current.End.Accept(fieldVisitor);
            }
            else
            {
                Console.WriteLine("There are no fields in the document.");
            }
        }
    }

    Console.WriteLine(fieldVisitor.GetText());

/// <summary>
/// 打印字段信息的文档访问者实现。
/// </summary>
public class FieldVisitor : DocumentVisitor
{
    public FieldVisitor()
    {
        mBuilder = new StringBuilder();
    }

    /// <summary>
    /// 获取访问者积累的文档的纯文本。
    /// </summary>
    public string GetText()
    {
        return mBuilder.ToString();
    }

    /// <summary>
    /// 在文档中遇到 FieldStart 节点时调用。
    /// </summary>
    public override VisitorAction VisitFieldStart(FieldStart fieldStart)
    {
        mBuilder.AppendLine("Found field: " + fieldStart.FieldType);
        mBuilder.AppendLine("\tField code: " + fieldStart.GetField().GetFieldCode());
        mBuilder.AppendLine("\tDisplayed as: " + fieldStart.GetField().Result);

        return VisitorAction.Continue;
    }

    /// <summary>
    /// 在文档中遇到 FieldSeparator 节点时调用。
    /// </summary>
    public override VisitorAction VisitFieldSeparator(FieldSeparator fieldSeparator)
    {
        mBuilder.AppendLine("\tFound separator: " + fieldSeparator.GetText());

        return VisitorAction.Continue;
    }

    /// <summary>
    /// 在文档中遇到 FieldEnd 节点时调用。
    /// </summary>
    public override VisitorAction VisitFieldEnd(FieldEnd fieldEnd)
    {
        mBuilder.AppendLine("End of field: " + fieldEnd.FieldType);

        return VisitorAction.Continue;
    }

    private readonly StringBuilder mBuilder;
}
```

### 也可以看看

* class [Field](../field/)
* 命名空间 [Aspose.Words.Fields](../../aspose.words.fields/)
* 部件 [Aspose.Words](../../)


