---
title: SmartTag.Accept
second_title: Aspose.Words for .NET API 参考
description: SmartTag 方法. 接受访客
type: docs
weight: 60
url: /zh/net/aspose.words.markup/smarttag/accept/
---
## SmartTag.Accept method

接受访客。

```csharp
public override bool Accept(DocumentVisitor visitor)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| visitor | DocumentVisitor | 将访问节点的访问者。 |

### 返回值

如果访问了所有节点，则为真；如果 DocumentVisitor 在访问所有节点之前停止操作，则返回 false。

### 评论

枚举此节点及其所有子节点。每个节点调用 DocumentVisitor 上的相应方法。

有关更多信息，请参阅访问者设计模式。

来电[`VisitSmartTagStart`](../../../aspose.words/documentvisitor/visitsmarttagstart/)，然后调用[`Accept`](../../../aspose.words/node/accept/)对于智能标签的所有 子节点并调用[`VisitSmartTagEnd`](../../../aspose.words/documentvisitor/visitsmarttagend/)最后.

### 例子

展示如何创建智能标签。

```csharp
public void Create()
{
    Document doc = new Document();

    // 智能标记出现在文档中，Microsoft Word 将其文本的一部分识别为某种形式的数据，
    // 例如姓名、日期或地址，并将其转换为显示紫色虚线下划线的超链接。
    SmartTag smartTag = new SmartTag(doc);

    // 智能标签是包含其识别文本的完整的复合节点。
    // 手动添加内容到这个智能标签。
    smartTag.AppendChild(new Run(doc, "May 29, 2019"));

    // Microsoft Word 可能会将上述内容识别为日期。
    // 智能标签使用“元素”属性来反映它们包含的数据类型。
    smartTag.Element = "date";

    // 一些智能标记类型将其内容进一步处理为自定义 XML 属性。
    smartTag.Properties.Add(new CustomXmlProperty("Day", string.Empty, "29"));
    smartTag.Properties.Add(new CustomXmlProperty("Month", string.Empty, "5"));
    smartTag.Properties.Add(new CustomXmlProperty("Year", string.Empty, "2019"));

    // 将智能标签的 URI 设置为默认值。
    smartTag.Uri = "urn:schemas-microsoft-com:office:smarttags";

    doc.FirstSection.Body.FirstParagraph.AppendChild(smartTag);
    doc.FirstSection.Body.FirstParagraph.AppendChild(new Run(doc, " is a date. "));

    // 为股票代码创建另一个智能标签。
    smartTag = new SmartTag(doc);
    smartTag.Element = "stockticker";
    smartTag.Uri = "urn:schemas-microsoft-com:office:smarttags";

    smartTag.AppendChild(new Run(doc, "MSFT"));

    doc.FirstSection.Body.FirstParagraph.AppendChild(smartTag);
    doc.FirstSection.Body.FirstParagraph.AppendChild(new Run(doc, " is a stock ticker."));

    // 使用文档访问者打印我们文档中的所有智能标签。
    doc.Accept(new SmartTagPrinter());

    // 旧版本的 Microsoft Word 支持智能标记。
    doc.Save(ArtifactsDir + "SmartTag.Create.doc");

    // 使用“RemoveSmartTags”方法从文档中删除所有智能标签。
    Assert.AreEqual(2, doc.GetChildNodes(NodeType.SmartTag, true).Count);

    doc.RemoveSmartTags();

    Assert.AreEqual(0, doc.GetChildNodes(NodeType.SmartTag, true).Count);
}

/// <summary>
/// 打印访问过的智能标签及其内容。
/// </summary>
private class SmartTagPrinter : DocumentVisitor
{
    /// <summary>
    /// 在文档中遇到 SmartTag 节点时调用。
    /// </summary>
    public override VisitorAction VisitSmartTagStart(SmartTag smartTag)
    {
        Console.WriteLine($"Smart tag type: {smartTag.Element}");
        return VisitorAction.Continue;
    }

    /// <summary>
    /// SmartTag节点访问结束时调用。
    /// </summary>
    public override VisitorAction VisitSmartTagEnd(SmartTag smartTag)
    {
        Console.WriteLine($"\tContents: \"{smartTag.ToString(SaveFormat.Text)}\"");

        if (smartTag.Properties.Count == 0)
        {
            Console.WriteLine("\tContains no properties");
        }
        else
        {
            Console.Write("\tProperties: ");
            string[] properties = new string[smartTag.Properties.Count];
            int index = 0;

            foreach (CustomXmlProperty cxp in smartTag.Properties)
                properties[index++] = $"\"{cxp.Name}\" = \"{cxp.Value}\"";

            Console.WriteLine(string.Join(", ", properties));
        }

        return VisitorAction.Continue;
    }
}
```

### 也可以看看

* class [DocumentVisitor](../../../aspose.words/documentvisitor/)
* class [SmartTag](../)
* 命名空间 [Aspose.Words.Markup](../../smarttag/)
* 部件 [Aspose.Words](../../../)


