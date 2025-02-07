---
title: AbsolutePositionTab.Accept
second_title: Aspose.Words for .NET API Referansı
description: AbsolutePositionTab yöntem. Bir ziyaretçiyi kabul eder.
type: docs
weight: 10
url: /tr/net/aspose.words/absolutepositiontab/accept/
---
## AbsolutePositionTab.Accept method

Bir ziyaretçiyi kabul eder.

```csharp
public override bool Accept(DocumentVisitor visitor)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| visitor | DocumentVisitor | Düğümü ziyaret edecek ziyaretçi. |

### Geri dönüş değeri

Ziyaretçi numaralandırmanın durmasını isterse yanlış.

### Notlar

DocumentVisitor.VisitAbsolutePositionTab'i çağırır.

Daha fazla bilgi için Ziyaretçi tasarım modeline bakın.

### Örnekler

Bir belge ziyaretçisiyle mutlak konum sekmesi karakterlerinin nasıl işleneceğini gösterir.

```csharp
public void DocumentToTxt()
{
    Document doc = new Document(MyDir + "Absolute position tab.docx");

    // Bu özel belge ziyaretçisini kabul ederek belgemizin metin içeriğini çıkarın.
    DocTextExtractor myDocTextExtractor = new DocTextExtractor();
    doc.FirstSection.Body.Accept(myDocTextExtractor);

    // Dize biçiminde eşdeğeri olmayan mutlak konum sekmesi, açıkça bir sekme karakterine dönüştürüldü.
    Assert.AreEqual("Before AbsolutePositionTab\tAfter AbsolutePositionTab", myDocTextExtractor.GetText());

    // Bir AbsolutePositionTab, bir DocumentVisitor'ı kendi başına da kabul edebilir.
    AbsolutePositionTab absPositionTab = (AbsolutePositionTab)doc.FirstSection.Body.FirstParagraph.GetChild(NodeType.SpecialChar, 0, true);

    myDocTextExtractor = new DocTextExtractor();
    absPositionTab.Accept(myDocTextExtractor);

    Assert.AreEqual("\t", myDocTextExtractor.GetText());
}

/// <summary>
/// Ziyaret edilen belgedeki tüm çalıştırmaların metin içeriğini toplar. Tüm mutlak sekme karakterlerini sıradan sekmelerle değiştirir.
/// </summary>
public class DocTextExtractor : DocumentVisitor
{
    public DocTextExtractor()
    {
        mBuilder = new StringBuilder();
    }

    /// <summary>
    /// Belgede bir Çalıştırma düğümüyle karşılaşıldığında çağrılır.
    /// </summary>
    public override VisitorAction VisitRun(Run run)
    {
        AppendText(run.Text);
        return VisitorAction.Continue;
    }

    /// <summary>
    /// Belgede bir AbsolutePositionTab düğümüyle karşılaşıldığında çağrılır.
    /// </summary>
    public override VisitorAction VisitAbsolutePositionTab(AbsolutePositionTab tab)
    {
        mBuilder.Append("\t");
        return VisitorAction.Continue;
    }

    /// <summary>
    /// Mevcut çıktıya metin ekler. Etkin/devre dışı çıkış bayrağını onurlandırır.
    /// </summary>
    private void AppendText(string text)
    {
        mBuilder.Append(text);
    }

    /// <summary>
    /// Ziyaretçi tarafından toplanan belgenin düz metni.
    /// </summary>
    public string GetText()
    {
        return mBuilder.ToString();
    }

    private readonly StringBuilder mBuilder;
}
```

### Ayrıca bakınız

* class [DocumentVisitor](../../documentvisitor/)
* class [AbsolutePositionTab](../)
* ad alanı [Aspose.Words](../../absolutepositiontab/)
* toplantı [Aspose.Words](../../../)


