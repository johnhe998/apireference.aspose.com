---
title: DocumentVisitor.VisitStructuredDocumentTagEnd
second_title: Aspose.Words لمراجع .NET API
description: DocumentVisitor طريقة. يتم استدعاؤها عند انتهاء تعداد علامة مستند منظم.
type: docs
weight: 440
url: /ar/net/aspose.words/documentvisitor/visitstructureddocumenttagend/
---
## DocumentVisitor.VisitStructuredDocumentTagEnd method

يتم استدعاؤها عند انتهاء تعداد علامة مستند منظم.

```csharp
public virtual VisitorAction VisitStructuredDocumentTagEnd(StructuredDocumentTag sdt)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| sdt | StructuredDocumentTag | الكائن الذي تتم زيارته. |

### قيمة الإرجاع

أ[`VisitorAction`](../../visitoraction/) القيمة التي تحدد كيفية متابعة التعداد.

### أمثلة

يوضح كيفية طباعة بنية العقدة لكل علامة مستند منظم في مستند.

```csharp
public void StructuredDocumentTagToText()
{
    Document doc = new Document(MyDir + "DocumentVisitor-compatible features.docx");
    StructuredDocumentTagNodePrinter visitor = new StructuredDocumentTagNodePrinter();

    // عندما نحصل على عقدة مركبة لقبول زائر المستند ، يزور الزائر عقدة القبول ،
    // ثم يعبر جميع أبناء العقدة بطريقة العمق أولاً.
    // يمكن للزائر قراءة كل عقدة تمت زيارتها وتعديلها.
    doc.Accept(visitor);

    Console.WriteLine(visitor.GetText());
}

/// <summary>
/// يتجاوز الشجرة غير الثنائية للعقد الفرعية للعقد.
/// ينشئ خريطة في شكل سلسلة لكل عقد StructuredDocumentTag وأطفالها.
/// </summary>
public class StructuredDocumentTagNodePrinter : DocumentVisitor
{
    public StructuredDocumentTagNodePrinter()
    {
        mBuilder = new StringBuilder();
        mVisitorIsInsideStructuredDocumentTag = false;
    }

    /// <summary>
    /// يحصل على النص العادي للمستند الذي قام الزائر بتجميعه.
    /// </summary>
    public string GetText()
    {
        return mBuilder.ToString();
    }

    /// <summary>
    /// يتم الاستدعاء عند مواجهة عقدة تشغيل في المستند.
    /// </summary>
    public override VisitorAction VisitRun(Run run)
    {
        if (mVisitorIsInsideStructuredDocumentTag) IndentAndAppendLine("[Run] \"" + run.GetText() + "\"");

        return VisitorAction.Continue;
    }

    /// <summary>
    /// يتم استدعاؤها عند مصادفة عقدة StructuredDocumentTag في المستند.
    /// </summary>
    public override VisitorAction VisitStructuredDocumentTagStart(StructuredDocumentTag sdt)
    {
        IndentAndAppendLine("[StructuredDocumentTag start] Title: " + sdt.Title);
        mDocTraversalDepth++;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// يتم استدعاؤها بعد زيارة جميع العقد الفرعية لعقدة StructuredDocumentTag.
    /// </summary>
    public override VisitorAction VisitStructuredDocumentTagEnd(StructuredDocumentTag sdt)
    {
        mDocTraversalDepth--;
        IndentAndAppendLine("[StructuredDocumentTag end]");

        return VisitorAction.Continue;
    }

    /// <summary>
    /// قم بإلحاق سطر بـ StringBuilder وقم بعمل مسافة بادئة له اعتمادًا على مدى عمق الزائر في شجرة المستند.
    /// </summary>
    /// < param name = "text" > < / param >
    private void IndentAndAppendLine(string text)
    {
        for (int i = 0; i < mDocTraversalDepth; i++) mBuilder.Append("|  ");

        mBuilder.AppendLine(text);
    }

    private readonly bool mVisitorIsInsideStructuredDocumentTag;
    private int mDocTraversalDepth;
    private readonly StringBuilder mBuilder;
}
```

### أنظر أيضا

* enum [VisitorAction](../../visitoraction/)
* class [StructuredDocumentTag](../../../aspose.words.markup/structureddocumenttag/)
* class [DocumentVisitor](../)
* مساحة الاسم [Aspose.Words](../../documentvisitor/)
* المجسم [Aspose.Words](../../../)


