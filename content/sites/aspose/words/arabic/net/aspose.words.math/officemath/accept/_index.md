---
title: OfficeMath.Accept
second_title: Aspose.Words لمراجع .NET API
description: OfficeMath طريقة. يقبل الزائر .
type: docs
weight: 70
url: /ar/net/aspose.words.math/officemath/accept/
---
## OfficeMath.Accept method

يقبل الزائر .

```csharp
public override bool Accept(DocumentVisitor visitor)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| visitor | DocumentVisitor | الزائر الذي سيزور العقد. |

### قيمة الإرجاع

صحيح إذا تمت زيارة جميع العقد ؛ خطأ إذا أوقف برنامج DocumentVisitor العملية قبل زيارة جميع العقد.

### ملاحظات

يعدّ فوق هذه العقدة وجميع توابعها. تستدعي كل عقدة طريقة مقابلة في DocumentVisitor.

لمزيد من المعلومات ، راجع نمط تصميم الزائر.

المكالمات[`VisitOfficeMathStart`](../../../aspose.words/documentvisitor/visitofficemathstart/) ثم المكالمات[`Accept`](../../../aspose.words/node/accept/) لجميع العقد الفرعية للرياضيات المكتبية والمكالمات all [`VisitOfficeMathEnd`](../../../aspose.words/documentvisitor/visitofficemathend/) في النهاية .

### أمثلة

يوضح كيفية طباعة بنية العقدة لكل عقدة رياضية للمكتب في مستند.

```csharp
public void OfficeMathToText()
{
    Document doc = new Document(MyDir + "DocumentVisitor-compatible features.docx");
    OfficeMathStructurePrinter visitor = new OfficeMathStructurePrinter();

    // عندما نحصل على عقدة مركبة لقبول زائر المستند ، يزور الزائر عقدة القبول ،
    // ثم يعبر جميع أبناء العقدة بطريقة العمق أولاً.
    // يمكن للزائر قراءة كل عقدة تمت زيارتها وتعديلها.
    doc.Accept(visitor);

    Console.WriteLine(visitor.GetText());
}

/// <summary>
/// يتجاوز الشجرة غير الثنائية للعقد الفرعية للعقد.
/// ينشئ خريطة في شكل سلسلة لجميع عقد OfficeMath التي تمت مواجهتها وأطفالها.
/// </summary>
public class OfficeMathStructurePrinter : DocumentVisitor
{
    public OfficeMathStructurePrinter()
    {
        mBuilder = new StringBuilder();
        mVisitorIsInsideOfficeMath = false;
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
        if (mVisitorIsInsideOfficeMath) IndentAndAppendLine("[Run] \"" + run.GetText() + "\"");

        return VisitorAction.Continue;
    }

    /// <summary>
    /// يتم الاستدعاء عند مصادفة عقدة OfficeMath في المستند.
    /// </summary>
    public override VisitorAction VisitOfficeMathStart(OfficeMath officeMath)
    {
        IndentAndAppendLine("[OfficeMath start] Math object type: " + officeMath.MathObjectType);
        mDocTraversalDepth++;
        mVisitorIsInsideOfficeMath = true;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// يتم استدعاؤها بعد زيارة جميع العقد الفرعية لعقدة OfficeMath.
    /// </summary>
    public override VisitorAction VisitOfficeMathEnd(OfficeMath officeMath)
    {
        mDocTraversalDepth--;
        IndentAndAppendLine("[OfficeMath end]");
        mVisitorIsInsideOfficeMath = false;

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

    private bool mVisitorIsInsideOfficeMath;
    private int mDocTraversalDepth;
    private readonly StringBuilder mBuilder;
}
```

### أنظر أيضا

* class [DocumentVisitor](../../../aspose.words/documentvisitor/)
* class [OfficeMath](../)
* مساحة الاسم [Aspose.Words.Math](../../officemath/)
* المجسم [Aspose.Words](../../../)


