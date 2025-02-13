---
title: Class SdtListItem
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Markup.SdtListItem 班级. 此元素指定父项中的单个列表项ComboBox或者DropDownList结构化文档标签
type: docs
weight: 3780
url: /zh/net/aspose.words.markup/sdtlistitem/
---
## SdtListItem class

此元素指定父项中的单个列表项ComboBox或者DropDownList结构化文档标签。

```csharp
public class SdtListItem
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [SdtListItem](sdtlistitem/#constructor)(string) | 初始化这个类的一个新实例。 |
| [SdtListItem](sdtlistitem/#constructor_1)(string, string) | 初始化这个类的一个新实例。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [DisplayText](../../aspose.words.markup/sdtlistitem/displaytext/) { get; } | 获取要在运行内容中显示的文本，以代替[`Value`](./value/)此列表项的属性内容。 |
| [Value](../../aspose.words.markup/sdtlistitem/value/) { get; } | 获取此列表项的值。 |

### 例子

展示如何使用下拉列表结构化文档标签。

```csharp
Document doc = new Document();
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.DropDownList, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(tag);

// 下拉列表结构化文档标签是一种允许用户
// 通过左键单击并在 Microsoft Word 中打开表单，从列表中选择一个选项。
// “ListItems”属性包含所有列表项，每个列表项都是一个“SdtListItem”。
SdtListItemCollection listItems = tag.ListItems;
listItems.Add(new SdtListItem("Value 1"));

Assert.AreEqual(listItems[0].DisplayText, listItems[0].Value);

// 再添加 3 个列表项。使用与第一项不同的构造函数初始化这些项
// 显示与其值不同的字符串。
listItems.Add(new SdtListItem("Item 2", "Value 2"));
listItems.Add(new SdtListItem("Item 3", "Value 3"));
listItems.Add(new SdtListItem("Item 4", "Value 4"));

Assert.AreEqual(4, listItems.Count);

// 下拉列表显示第一项。将不同的列表项分配给“SelectedValue”以显示它。
listItems.SelectedValue = listItems[3];

Assert.AreEqual("Value 4", listItems.SelectedValue.Value);

// 枚举集合并打印每个元素。
using (IEnumerator<SdtListItem> enumerator = listItems.GetEnumerator())
{
    while (enumerator.MoveNext())
        if (enumerator.Current != null)
            Console.WriteLine($"List item: {enumerator.Current.DisplayText}, value: {enumerator.Current.Value}");
}

 // 删除最后一个列表项。
listItems.RemoveAt(3);

Assert.AreEqual(3, listItems.Count);

// 因为我们的下拉控件默认设置为显示被移除的项，所以给它一个要显示的项，它存在。
listItems.SelectedValue = listItems[1];

doc.Save(ArtifactsDir + "StructuredDocumentTag.ListItemCollection.docx");

// 使用“清除”方法一次清空整个下拉项集合。
listItems.Clear();

Assert.AreEqual(0, listItems.Count);
```

### 也可以看看

* 命名空间 [Aspose.Words.Markup](../../aspose.words.markup/)
* 部件 [Aspose.Words](../../)


