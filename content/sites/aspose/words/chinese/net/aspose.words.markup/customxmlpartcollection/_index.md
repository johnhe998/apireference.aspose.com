---
title: Class CustomXmlPartCollection
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Markup.CustomXmlPartCollection 班级. 表示自定义 XML 部件的集合项目是CustomXmlPart对象.
type: docs
weight: 3690
url: /zh/net/aspose.words.markup/customxmlpartcollection/
---
## CustomXmlPartCollection class

表示自定义 XML 部件的集合。项目是[`CustomXmlPart`](../customxmlpart/)对象.

```csharp
public class CustomXmlPartCollection : IEnumerable<CustomXmlPart>
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [CustomXmlPartCollection](customxmlpartcollection/)() | 默认构造函数。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Count](../../aspose.words.markup/customxmlpartcollection/count/) { get; } | 获取集合中包含的元素数。 |
| [Item](../../aspose.words.markup/customxmlpartcollection/item/) { get; set; } | 获取或设置指定索引处的项目。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [Add](../../aspose.words.markup/customxmlpartcollection/add/#add_1)(CustomXmlPart) | 将一个项目添加到集合中。 |
| [Add](../../aspose.words.markup/customxmlpartcollection/add/#add)(string, string) | 使用指定的 XML 创建一个新的 XML 部件并将其添加到集合中。 |
| [Clear](../../aspose.words.markup/customxmlpartcollection/clear/)() | 从集合中删除所有元素。 |
| [Clone](../../aspose.words.markup/customxmlpartcollection/clone/)() | 制作此集合及其项目的深层副本。 |
| [GetById](../../aspose.words.markup/customxmlpartcollection/getbyid/)(string) | 按标识符查找并返回自定义 XML 部分。 |
| [GetEnumerator](../../aspose.words.markup/customxmlpartcollection/getenumerator/)() | 返回一个可用于迭代集合中所有项目的枚举器对象。 |
| [RemoveAt](../../aspose.words.markup/customxmlpartcollection/removeat/)(int) | 删除指定索引处的项目。 |

### 评论

您通常不需要创建此类的实例。您可以通过以下方式访问存储在文档中的自定义 XML 数据 [`CustomXmlParts`](../../aspose.words/document/customxmlparts/)财产。

### 例子

展示如何使用自定义 XML 数据创建结构化文档标签。

```csharp
Document doc = new Document();

// 构造一个包含数据的 XML 部分并将其添加到文档的集合中。
// 如果我们在 Microsoft Word 中启用“开发者”选项卡，
// 我们可以在“XML Mapping Pane”中找到这个集合中的元素，以及一些默认元素。
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Hello world!</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);

Assert.AreEqual(Encoding.ASCII.GetBytes(xmlPartContent), xmlPart.Data);
Assert.AreEqual(xmlPartId, xmlPart.Id);

// 下面是引用 XML 部分的两种方法。
// 1 - 通过自定义 XML 部件集合中的索引：
Assert.AreEqual(xmlPart, doc.CustomXmlParts[0]);

// 2 - 通过 GUID：
Assert.AreEqual(xmlPart, doc.CustomXmlParts.GetById(xmlPartId));

// 添加一个 XML 模式关联。
xmlPart.Schemas.Add("http://www.w3.org/2001/XMLSchema");

// 克隆一部分，然后将其插入到集合中。
CustomXmlPart xmlPartClone = xmlPart.Clone();
xmlPartClone.Id = Guid.NewGuid().ToString("B");
doc.CustomXmlParts.Add(xmlPartClone);

Assert.AreEqual(2, doc.CustomXmlParts.Count);

// 遍历集合并打印每个部分的内容。
using (IEnumerator<CustomXmlPart> enumerator = doc.CustomXmlParts.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"XML part index {index}, ID: {enumerator.Current.Id}");
        Console.WriteLine($"\tContent: {Encoding.UTF8.GetString(enumerator.Current.Data)}");
        index++;
    }
}

// 使用“RemoveAt”方法按索引删除克隆的部分。
doc.CustomXmlParts.RemoveAt(1);

Assert.AreEqual(1, doc.CustomXmlParts.Count);

// 克隆 XML 部件集合，然后使用“Clear”方法一次删除其所有元素。
CustomXmlPartCollection customXmlParts = doc.CustomXmlParts.Clone();
customXmlParts.Clear();

// 创建一个结构化的文档标签，它将显示我们部分的内容并将其插入到文档正文中。
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
tag.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", string.Empty);

doc.FirstSection.Body.AppendChild(tag);

doc.Save(ArtifactsDir + "StructuredDocumentTag.CustomXml.docx");
```

### 也可以看看

* class [CustomXmlPart](../customxmlpart/)
* 命名空间 [Aspose.Words.Markup](../../aspose.words.markup/)
* 部件 [Aspose.Words](../../)


