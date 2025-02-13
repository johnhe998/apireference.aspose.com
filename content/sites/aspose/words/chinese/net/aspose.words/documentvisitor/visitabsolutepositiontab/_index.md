---
title: DocumentVisitor.VisitAbsolutePositionTab
second_title: Aspose.Words for .NET API 参考
description: DocumentVisitor 方法. 当一个AbsolutePositionTab在文档中遇到节点
type: docs
weight: 10
url: /zh/net/aspose.words/documentvisitor/visitabsolutepositiontab/
---
## DocumentVisitor.VisitAbsolutePositionTab method

当一个[`AbsolutePositionTab`](../../absolutepositiontab/)在文档中遇到节点。

```csharp
public virtual VisitorAction VisitAbsolutePositionTab(AbsolutePositionTab tab)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| tab | AbsolutePositionTab | 正在访问的对象。 |

### 返回值

一个[`VisitorAction`](../../visitoraction/)指定如何继续枚举的值。

### 例子

显示如何使用文档访问者处理绝对位置制表符。

```csharp
public void DocumentToTxt()
{
    Document doc = new Document(MyDir + "Absolute position tab.docx");

    // 通过接受这个自定义文档访问者来提取我们文档的文本内容。
    DocTextExtractor myDocTextExtractor = new DocTextExtractor();
    doc.FirstSection.Body.Accept(myDocTextExtractor);

    // 绝对位置制表符，在字符串形式中没有等价物，已显式转换为制表符。
    Assert.AreEqual("Before AbsolutePositionTab\tAfter AbsolutePositionTab", myDocTextExtractor.GetText());

    // AbsolutePositionTab 本身也可以接受 DocumentVisitor。
    AbsolutePositionTab absPositionTab = (AbsolutePositionTab)doc.FirstSection.Body.FirstParagraph.GetChild(NodeType.SpecialChar, 0, true);

    myDocTextExtractor = new DocTextExtractor();
    absPositionTab.Accept(myDocTextExtractor);

    Assert.AreEqual("\t", myDocTextExtractor.GetText());
}

/// <summary>
/// 收集访问文档中所有运行的文本内容。用普通制表符替换所有绝对制表符。
/// </summary>
public class DocTextExtractor : DocumentVisitor
{
    public DocTextExtractor()
    {
        mBuilder = new StringBuilder();
    }

    /// <summary>
    /// 在文档中遇到 Run 节点时调用。
    /// </summary>
    public override VisitorAction VisitRun(Run run)
    {
        AppendText(run.Text);
        return VisitorAction.Continue;
    }

    /// <summary>
    /// 在文档中遇到 AbsolutePositionTab 节点时调用。
    /// </summary>
    public override VisitorAction VisitAbsolutePositionTab(AbsolutePositionTab tab)
    {
        mBuilder.Append("\t");
        return VisitorAction.Continue;
    }

    /// <summary>
    /// 将文本添加到当前输出。尊重启用/禁用的输出标志。
    /// </summary>
    private void AppendText(string text)
    {
        mBuilder.Append(text);
    }

    /// <summary>
    /// 访问者积累的文档的纯文本。
    /// </summary>
    public string GetText()
    {
        return mBuilder.ToString();
    }

    private readonly StringBuilder mBuilder;
}
```

### 也可以看看

* enum [VisitorAction](../../visitoraction/)
* class [AbsolutePositionTab](../../absolutepositiontab/)
* class [DocumentVisitor](../)
* 命名空间 [Aspose.Words](../../documentvisitor/)
* 部件 [Aspose.Words](../../../)


