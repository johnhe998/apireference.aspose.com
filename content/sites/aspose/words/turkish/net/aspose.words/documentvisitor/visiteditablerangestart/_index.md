---
title: DocumentVisitor.VisitEditableRangeStart
second_title: Aspose.Words for .NET API Referansı
description: DocumentVisitor yöntem. Belgede düzenlenebilir bir aralığın başlangıcıyla karşılaşıldığında çağrılır.
type: docs
weight: 170
url: /tr/net/aspose.words/documentvisitor/visiteditablerangestart/
---
## DocumentVisitor.VisitEditableRangeStart method

Belgede düzenlenebilir bir aralığın başlangıcıyla karşılaşıldığında çağrılır.

```csharp
public virtual VisitorAction VisitEditableRangeStart(EditableRangeStart editableRangeStart)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| editableRangeStart | EditableRangeStart | Ziyaret edilen nesne. |

### Geri dönüş değeri

A[`VisitorAction`](../../visitoraction/) numaralandırmaya nasıl devam edileceğini belirten değer.

### Örnekler

Bir belgedeki her düzenlenebilir aralığın düğüm yapısının nasıl yazdırılacağını gösterir.

```csharp
public void EditableRangeToText()
{
    Document doc = new Document(MyDir + "DocumentVisitor-compatible features.docx");
    EditableRangeStructurePrinter visitor = new EditableRangeStructurePrinter();

    // Bir belge ziyaretçisini kabul etmek için bir bileşik düğüm aldığımızda, ziyaretçi kabul eden düğümü ziyaret eder,
    // ve ardından tüm düğümün alt öğelerini derinlik öncelikli bir şekilde çaprazlar.
    // Ziyaretçi, ziyaret edilen her düğümü okuyabilir ve değiştirebilir.
    doc.Accept(visitor);

    Console.WriteLine(visitor.GetText());
}

/// <summary>
/// Bir düğümün ikili olmayan alt düğümler ağacında çapraz geçiş yapar.
/// Karşılaşılan tüm EditableRange düğümlerinin ve bunların alt öğelerinin bir dizesi biçiminde bir harita oluşturur.
/// </summary>
public class EditableRangeStructurePrinter : DocumentVisitor
{
    public EditableRangeStructurePrinter()
    {
        mBuilder = new StringBuilder();
        mVisitorIsInsideEditableRange = false;
    }

    /// <summary>
    /// Ziyaretçi tarafından toplanan belgenin düz metnini alır.
    /// </summary>
    public string GetText()
    {
        return mBuilder.ToString();
    }

    /// <summary>
    /// Belgede bir Çalıştırma düğümüyle karşılaşıldığında çağrılır.
    /// </summary>
    public override VisitorAction VisitRun(Run run)
    {
        // Çalıştırma içeriklerini yazdırmak istiyoruz, ancak metin kutularında olduğu gibi yalnızca şekillerin içindeyseler
        if (mVisitorIsInsideEditableRange) IndentAndAppendLine("[Run] \"" + run.GetText() + "\"");

        return VisitorAction.Continue;
    }

    /// <summary>
    /// Belgede bir EditableRange düğümüyle karşılaşıldığında çağrılır.
    /// </summary>
    public override VisitorAction VisitEditableRangeStart(EditableRangeStart editableRangeStart)
    {
        IndentAndAppendLine("[EditableRange start] ID: " + editableRangeStart.Id + " Owner: " +
                            editableRangeStart.EditableRange.SingleUser);
        mDocTraversalDepth++;
        mVisitorIsInsideEditableRange = true;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// EditableRange düğümünün ziyareti sona erdiğinde çağrılır.
    /// </summary>
    public override VisitorAction VisitEditableRangeEnd(EditableRangeEnd editableRangeEnd)
    {
        mDocTraversalDepth--;
        IndentAndAppendLine("[EditableRange end]");
        mVisitorIsInsideEditableRange = false;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// StringBuilder'a bir satır ekleyin ve ziyaretçinin belge ağacında ne kadar derin olduğuna bağlı olarak girinti yapın.
    /// </summary>
    /// <param name="metin"></param>
    private void IndentAndAppendLine(string text)
    {
        for (int i = 0; i < mDocTraversalDepth; i++) mBuilder.Append("|  ");

        mBuilder.AppendLine(text);
    }

    private bool mVisitorIsInsideEditableRange;
    private int mDocTraversalDepth;
    private readonly StringBuilder mBuilder;
}
```

### Ayrıca bakınız

* enum [VisitorAction](../../visitoraction/)
* class [EditableRangeStart](../../editablerangestart/)
* class [DocumentVisitor](../)
* ad alanı [Aspose.Words](../../documentvisitor/)
* toplantı [Aspose.Words](../../../)


